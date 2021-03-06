---
UID: NF:wdfinterrupt.WdfInterruptGetInfo
title: WdfInterruptGetInfo function
author: windows-driver-content
description: The WdfInterruptGetInfo method retrieves information about a specified interrupt.
old-location: wdf\wdfinterruptgetinfo.htm
old-project: wdf
ms.assetid: 11f086af-bda7-4dab-8c4b-0db2e89588d1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFInterruptObjectRef_eb163aa0-1ba3-491d-b215-85c8773dcfc9.xml, wdfinterrupt/WdfInterruptGetInfo, WdfInterruptGetInfo, PFN_WDFINTERRUPTGETINFO, WdfInterruptGetInfo method, kmdf.wdfinterruptgetinfo, wdf.wdfinterruptgetinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname: 
-	WdfInterruptGetInfo
product: Windows
targetos: Windows
req.typenames: *PWDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptGetInfo function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptGetInfo</b> method retrieves information about a specified interrupt.


## -syntax


````
VOID WdfInterruptGetInfo(
  _In_  WDFINTERRUPT        Interrupt,
  _Out_ PWDF_INTERRUPT_INFO Info
);
````


## -parameters




### -param Interrupt [in]

A handle to the interrupt object.


### -param Info [out]

A pointer to a caller-allocated <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure that has been initialized by calling <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_info_init.md">WDF_INTERRUPT_INFO_INIT</a>.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


The <b>WdfInterruptGetInfo</b> method can obtain interrupt information only if your driver calls it after the framework has called the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function and before the framework has called the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function. 

After <b>WdfInterruptGetInfo</b> has returned, the driver can identify passive level interrupt objects by examining the <b>Irql</b> member of the  <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure. For passive level interrupt objects, this value is PASSIVE_LEVEL.

For information about the order in which a driver's callback functions are called, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.



## -see-also

<a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>

<a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_info_init.md">WDF_INTERRUPT_INFO_INIT</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptGetInfo method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

