---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEDEVICE_0003
title: PFND3D12DDI_CREATEDEVICE_0003
author: windows-driver-content
description: The PFND3D12DDI_CREATEDEVICE_0003 function creates a graphics context that is referenced in subsequent calls.
old-location: display\pfnd3d12ddi_createdevice_0003.htm
old-project: display
ms.assetid: 5F25CFE0-00C5-45CD-8EA1-50F01BA4EA0B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_createdevice_0003, PFND3D12DDI_CREATEDEVICE_0003 callback function [Display Devices], PFND3D12DDI_CREATEDEVICE_0003, d3d12umddi/PFND3D12DDI_CREATEDEVICE_0003
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3d12umddi.h
apiname: 
-	PFND3D12DDI_CREATEDEVICE_0003
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEDEVICE_0003 callback


## -description


The PFND3D12DDI_CREATEDEVICE_0003 function creates a graphics context that is referenced in subsequent calls.


## -prototype


````
HRESULT APIENTRY PFND3D12DDI_CREATEDEVICE_0003(
             D3D12DDI_HADAPTER             hAdapter,
  _In_ const D3D12DDIARG_CREATEDEVICE_0003 *pCreateData
);
````


## -parameters




### -param D3D12DDI_HADAPTER



### -param *






#### - pCreateData [in]

A pointer to a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_createdevice_0003.md">D3D12DDIARG_CREATEDEVICE</a> structure.


#### - hAdapter

A handle to the graphics adapter object that was created with the <a href="https://msdn.microsoft.com/library/windows/hardware/mt779071">PFND3D12DDI_OPENADAPTER</a> function.


## -returns



             PFND3D12DDI_CREATEDEVICE_0003 returns one of the following values:
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
The graphics context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DXGI_STATUS_NO_REDIRECTION</b></dt>
</dl>
</td>
<td width="60%">
The graphics context was successfully created. However, the DirectX Graphics Infrastructure (DXGI) should not use the shared resource presentation path to effect communication with the Desktop Windows Manager (DWM). For more information about the DXGI DDI, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

                PFND3D12DDI_CREATEDEVICE_0003 could not allocate the memory that was required for it to complete.

</td>
</tr>
</table> 


