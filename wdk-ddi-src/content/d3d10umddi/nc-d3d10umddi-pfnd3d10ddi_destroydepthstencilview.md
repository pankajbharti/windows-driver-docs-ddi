---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYDEPTHSTENCILVIEW
title: PFND3D10DDI_DESTROYDEPTHSTENCILVIEW
author: windows-driver-content
description: The DestroyDepthStencilView function destroys the specified depth stencil view object. The depth stencil view object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroydepthstencilview.htm
old-project: display
ms.assetid: 5cd2b7bd-0231-4f00-a54e-960b9bffa98e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroydepthstencilview, DestroyDepthStencilView callback function [Display Devices], DestroyDepthStencilView, PFND3D10DDI_DESTROYDEPTHSTENCILVIEW, PFND3D10DDI_DESTROYDEPTHSTENCILVIEW, d3d10umddi/DestroyDepthStencilView, UserModeDisplayDriverDx10_Functions_140d9da4-c965-4f51-b16c-1c29ff6e2e94.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3d10umddi.h
apiname: 
-	DestroyDepthStencilView
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10DDI_DESTROYDEPTHSTENCILVIEW callback


## -description


The <b>DestroyDepthStencilView</b> function destroys the specified depth stencil view object. The depth stencil view object can be destoyed only if it is not currently bound to a display device. 


## -prototype


````
PFND3D10DDI_DESTROYDEPTHSTENCILVIEW DestroyDepthStencilView;

VOID APIENTRY DestroyDepthStencilView(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D10DDI_HDEPTHSTENCILVIEW hDepthStencilView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D10DDI_HDEPTHSTENCILVIEW






#### - hDepthStencilView [in]

 A handle to the driver's private data for the depth stencil view object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroyDepthStencilView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_DESTROYDEPTHSTENCILVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

