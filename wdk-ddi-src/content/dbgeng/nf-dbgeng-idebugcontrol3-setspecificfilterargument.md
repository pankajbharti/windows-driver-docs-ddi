---
UID: NF:dbgeng.IDebugControl3.SetSpecificFilterArgument
title: IDebugControl3::SetSpecificFilterArgument method
author: windows-driver-content
description: The SetSpecificFilterArgument method sets the value of filter argument for the specific filters that can have an argument.
old-location: debugger\setspecificfilterargument.htm
old-project: debugger
ms.assetid: 99731ad4-1023-4225-a133-3cb73e3ad07f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetSpecificFilterArgument method [Windows Debugging], IDebugControl2 interface, SetSpecificFilterArgument method [Windows Debugging], IDebugControl3 interface, IDebugControl::SetSpecificFilterArgument, IDebugControl2::SetSpecificFilterArgument, SetSpecificFilterArgument method [Windows Debugging], IDebugControl interface, SetSpecificFilterArgument, SetSpecificFilterArgument method [Windows Debugging], IDebugControl3, dbgeng/IDebugControl::SetSpecificFilterArgument, IDebugControl3 interface [Windows Debugging], SetSpecificFilterArgument method, IDebugControl2 interface [Windows Debugging], SetSpecificFilterArgument method, IDebugControl interface [Windows Debugging], SetSpecificFilterArgument method, dbgeng/IDebugControl3::SetSpecificFilterArgument, debugger.setspecificfilterargument, IDebugControl_a7f790fa-29f1-46f2-9163-a4b99f4880da.xml, IDebugControl3::SetSpecificFilterArgument, dbgeng/IDebugControl2::SetSpecificFilterArgument
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	dbgeng.h
apiname: 
-	IDebugControl.SetSpecificFilterArgument
-	IDebugControl2.SetSpecificFilterArgument
-	IDebugControl3.SetSpecificFilterArgument
product: Windows
targetos: Windows
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::SetSpecificFilterArgument method


## -description


The <b>SetSpecificFilterArgument</b>  method sets the value of filter argument for the specific filters that can have an argument.


## -syntax


````
HRESULT SetSpecificFilterArgument(
  [in] ULONG Index,
  [in] PCSTR Argument
);
````


## -parameters




### -param Index [in]

Specifies the index of the specific filter whose argument will be set.  <i>Index</i> must be the index of a specific filter that has an argument.


### -param Argument [in]

Specifies the argument for the specific filter.  The interpretation of this argument depends on the specific filter.


## -returns


This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> does not refer to a specific filter that has an argument.

</td>
</tr>
</table> 



## -remarks


For a list of specific filters that have argument and the interpretation of those arguments, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548386">GetSpecificFilterArgument</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetSpecificFilterArgument method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

