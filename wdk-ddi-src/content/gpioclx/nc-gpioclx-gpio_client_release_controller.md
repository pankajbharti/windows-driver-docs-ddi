---
UID: NC:gpioclx.GPIO_CLIENT_RELEASE_CONTROLLER
title: GPIO_CLIENT_RELEASE_CONTROLLER
author: windows-driver-content
description: The CLIENT_ReleaseController event callback function performs operations that are needed when the general-purpose I/O (GPIO) controller device is no longer accessible.
old-location: gpio\client_releasecontroller.htm
old-project: GPIO
ms.assetid: DC73A00D-F7FA-492A-ABAF-04A5CFD85881
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_releasecontroller, CLIENT_ReleaseController callback function [Parallel Ports], CLIENT_ReleaseController, GPIO_CLIENT_RELEASE_CONTROLLER, GPIO_CLIENT_RELEASE_CONTROLLER, gpioclx/CLIENT_ReleaseController
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at PASSIVE_LEVEL.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Gpioclx.h
apiname: 
-	CLIENT_ReleaseController
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_RELEASE_CONTROLLER callback


## -description


The <i>CLIENT_ReleaseController</i> event callback function performs operations that are needed when the general-purpose I/O (GPIO) controller device is no longer accessible.


## -prototype


````
GPIO_CLIENT_RELEASE_CONTROLLER CLIENT_ReleaseController;

NTSTATUS CLIENT_ReleaseController(
  _In_ WDFDEVICE Device,
  _In_ PVOID     Context
)
{ ... }
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the GPIO controller.


### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


## -returns


The <i>CLIENT_ReleaseController</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.



## -remarks


This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function after the GPIO controller device is no longer accessible.

During the <i>CLIENT_ReleaseController</i> callback, the GPIO controller driver should release any hardware resources that it acquired as a result of the preceding call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439389">CLIENT_PrepareController</a> callback function. In the case of a memory-mapped GPIO controller device, the driver should unmap the memory address range or ranges that are assigned to the hardware registers. For a controller that is not memory-mapped, the driver should close the previously opened logical connection to the controller.

To register your driver's <i>CLIENT_ReleaseController</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_ReleaseController</i> function pointer.

Although the <i>CLIENT_ReleaseController</i> callback function is called at IRQL = PASSIVE_LEVEL, you should not make this function pageable. The <i>CLIENT_ReleaseController</i> callback is in the critical timing path for restoring power to the devices in the hardware platform and, for performance reasons, it should not be delayed by page faults.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ReleaseController callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

