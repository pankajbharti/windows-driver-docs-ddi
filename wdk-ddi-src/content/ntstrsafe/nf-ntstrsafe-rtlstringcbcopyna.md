---
UID: NF:ntstrsafe.RtlStringCbCopyNA
title: RtlStringCbCopyNA function
author: windows-driver-content
description: The RtlStringCbCopyNW and RtlStringCbCopyNA functions copy a byte-counted string to a buffer while limiting the size of the copied string.
old-location: kernel\rtlstringcbcopyn.htm
old-project: kernel
ms.assetid: d64fb3e6-fba1-4383-bdb0-a63dc7c16033
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbCopyNA, RtlStringCbCopyNW function [Kernel-Mode Driver Architecture], ntstrsafe/RtlStringCbCopyNA, RtlStringCbCopyN, RtlStringCbCopyNW, safestrings_a3f7f7a8-b4a1-4c7c-b384-2243b3c97a4e.xml, ntstrsafe/RtlStringCbCopyNW, kernel.rtlstringcbcopyn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCopyNW (Unicode) and RtlStringCbCopyNA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ntstrsafe.lib
-	Ntstrsafe.dll
apiname: 
-	RtlStringCbCopyNW
-	RtlStringCbCopyNA
-	RtlStringCbCopyNW
product: Windows
targetos: Windows
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlStringCbCopyNA function


## -description


The <b>RtlStringCbCopyNW</b> and <b>RtlStringCbCopyNA</b> functions copy a byte-counted string to a buffer while limiting the size of the copied string.


## -syntax


````
NTSTATUS RtlStringCbCopyNW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cbDest,
  _In_  LPCTSTR pszSrc,
  _In_  size_t  cbSrc
);
````


## -parameters




### -param pszDest [out]

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i>, up to <i>cbSrc</i> bytes, is copied to the buffer at <i>pszDest</i> and terminated with a null character. 


### -param cbDest [in]

The size, in bytes, of the destination buffer. The buffer must be large enough for both the string and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * <b>sizeof</b>(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * <b>sizeof</b>(<b>char</b>). 


### -param pszSrc [in]

A pointer to a caller-supplied, null-terminated string. 


### -param cbToCopy

TBD



#### - cbSrc [in]

The maximum number of bytes to copy from <i>pszSrc</i> to <i>pszDest</i>.


## -returns


The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the copied string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

<ul>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table> 



## -remarks


<b>RtlStringCbCopyNW</b> and <b>RtlStringCbCopyNA</b> should be used instead of <b>strncpy</b>. However, these functions  differ in behavior. If <i>cbSrc</i> is larger than the number of bytes in <i>pszSrc</i>, the <b>RtlStringCbCopyN </b>functions—unlike <b>strncpy</b>—do not fill <i>pszDest</i> with null characters until <i>cbSrc</i> bytes have been copied.

<b>RtlStringCbCopyN</b> copies a given number of bytes from a source string. The size, in bytes, of the destination buffer is provided to the function to ensure that <b>RtlStringCbCopyN</b> does not write past the end of this buffer.

Use <b>RtlStringCbCopyNW</b> to handle Unicode strings and <b>RtlStringCbCopyNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.
<table>
<tr>
<th>String data type</th>
<th>String literal</th>
<th>Function</th>
</tr>
<tr>
<td>
WCHAR

</td>
<td>
L"string"

</td>
<td>
<b>RtlStringCbCopyNW</b>

</td>
</tr>
<tr>
<td>
<b>char</b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCbCopyNA</b>

</td>
</tr>
</table> 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, see <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopynexw.md">RtlStringCbCopyNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.



## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopynexw.md">RtlStringCbCopyNEx</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynw.md">RtlStringCchCopyN</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyw.md">RtlStringCbCopy</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCopyNW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

