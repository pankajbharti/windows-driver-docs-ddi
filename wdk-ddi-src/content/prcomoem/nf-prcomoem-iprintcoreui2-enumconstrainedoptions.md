---
UID: NF:prcomoem.IPrintCoreUI2.EnumConstrainedOptions
title: IPrintCoreUI2::EnumConstrainedOptions method
author: windows-driver-content
description: The IPrintCoreUI2::EnumConstrainedOptions method determines which options of a feature are constrained.
old-location: print\iprintcoreui2_enumconstrainedoptions.htm
old-project: print
ms.assetid: 815a20f4-9bd7-4f8d-8444-545097d1c4b3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintCoreUI2::EnumConstrainedOptions, print_unidrv-pscript_ui_43a11382-d457-4845-aaa0-4eb87a11929a.xml, EnumConstrainedOptions, print.iprintcoreui2_enumconstrainedoptions, IPrintCoreUI2 interface [Print Devices], EnumConstrainedOptions method, EnumConstrainedOptions method [Print Devices], IPrintCoreUI2 interface, IPrintCoreUI2, prcomoem/IPrintCoreUI2::EnumConstrainedOptions, EnumConstrainedOptions method [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	prcomoem.h
apiname: 
-	IPrintCoreUI2.EnumConstrainedOptions
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreUI2::EnumConstrainedOptions method


## -description


The <code>IPrintCoreUI2::EnumConstrainedOptions</code> method determines which options of a feature are constrained.


## -syntax


````
HRESULT EnumConstrainedOptions(
  [in]  POEMUIOBJ poemuiobj,
  [in]  DWORD     dwFlags,
  [in]  PCSTR     pszFeatureKeyword,
  [out] PSTR      pmszConstrainedOptionList,
  [in]  DWORD     cbSize,
  [out] PDWORD    pcbNeeded
);
````


## -parameters




### -param poemuiobj [in]

Pointer to the current context, an <a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pszFeatureKeyword [in]

Pointer to a caller-supplied buffer containing the single feature keyword of interest to the caller.


### -param pmszConstrainedOptionList [out]

Pointer to a caller-supplied buffer that receives the list of option keywords, in MULTI_SZ format, for this feature. Each keyword represents an option that is constrained in the current configuration. 

Set this parameter to <b>NULL</b> to simply query for the size (*<i>pcbNeeded</i>) of the constrained option list without having the list filled in.


### -param cbSize [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszConstrainedOptionList</i>. 


### -param pcbNeeded [out]

Pointer to a memory location that receives the actual size, in bytes, of the constrained option list.


## -returns


This method must return one of the following values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded. The method should also return this value if none of the feature's options are constrained. In this case, the method should place one null character into the buffer pointed to by <i>pmszConstrainedOptionList</i>, and should set *<i>pcbNeeded</i> to 1.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszConstrainedOptionList</i>).

The method was called with <i>pmszConstrainedOptionList</i> set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The string pointed to by <i>pszFeatureKeyword</i> was not a recognized feature.

The <i>poemuiobj</i> parameter pointed to an invalid context object.

The stickiness of the feature did not match that of the context object pointed to by <i>peomuiobj</i>. (See <a href="https://msdn.microsoft.com/b7f79841-f82c-4a60-9c2f-58772a65a5eb">Replacing Driver-Supplied Property Sheet Pages</a>.)

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The method failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not supported.

</td>
</tr>
</table> 



## -remarks


This method is supported only for Windows XP Pscript5 UI plug-ins that fully replace the core driver's standard UI pages, and is supported only during the UI plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> functions, and their property sheet callback routines. See <a href="https://msdn.microsoft.com/b7f79841-f82c-4a60-9c2f-58772a65a5eb">Replacing Driver-Supplied Property Sheet Pages</a> for more information.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553087">IPrintCoreUI2::WhyConstrained</a>

<a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::EnumConstrainedOptions method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

