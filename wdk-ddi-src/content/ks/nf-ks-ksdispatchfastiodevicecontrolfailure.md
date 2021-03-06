---
UID: NF:ks.KsDispatchFastIoDeviceControlFailure
title: KsDispatchFastIoDeviceControlFailure function
author: windows-driver-content
description: The KsDispatchFastIoDeviceControlFailure function is used in a KSDISPATCH_TABLE.FastDeviceIoControl entry that are not handled. The function should always return FALSE.
old-location: stream\ksdispatchfastiodevicecontrolfailure.htm
old-project: stream
ms.assetid: 7fb83c8d-e815-46c6-8011-75b25a4c0dd7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_f8510e75-1698-4ce9-acd8-d5db73a7c035.xml, KsDispatchFastIoDeviceControlFailure function [Streaming Media Devices], KsDispatchFastIoDeviceControlFailure, ks/KsDispatchFastIoDeviceControlFailure, stream.ksdispatchfastiodevicecontrolfailure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ks.lib
-	Ks.dll
apiname: 
-	KsDispatchFastIoDeviceControlFailure
product: Windows
targetos: Windows
req.typenames: 
---

# KsDispatchFastIoDeviceControlFailure function


## -description


The <b>KsDispatchFastIoDeviceControlFailure</b> function is used in a KSDISPATCH_TABLE.FastDeviceIoControl entry that are not handled. The function should always return <b>FALSE</b>. 


## -syntax


````
BOOLEAN KsDispatchFastIoDeviceControlFailure(
  _In_      PFILE_OBJECT     FileObject,
  _In_      BOOLEAN          Wait,
  _In_opt_  PVOID            InputBuffer,
  _In_      ULONG            InputBufferLength,
  _Out_opt_ PVOID            OutputBuffer,
  _In_      ULONG            OutputBufferLength,
  _In_      ULONG            IoControlCode,
  _Out_     PIO_STATUS_BLOCK IoStatus,
  _In_      PDEVICE_OBJECT   DeviceObject
);
````


## -parameters




### -param FileObject [in]

Not used.


### -param Wait [in]

Not used.


### -param InputBuffer [in, optional]

Not used.


### -param InputBufferLength [in]

Not used.


### -param OutputBuffer [out, optional]

Not used.


### -param OutputBufferLength [in]

Not used.


### -param IoControlCode [in]

Not used.


### -param IoStatus [out]

Not used.


### -param DeviceObject [in]

Not used.


## -returns


The <b>KsDispatchFastIoDeviceControlFailure</b> function returns <b>FALSE</b>.



## -remarks


The <b>KsDispatchFastIoDeviceControlFailure</b> function is needed since the dispatch table for a particular opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function, such as the <b>KsDispatchFastIoDeviceControlFailure</b> function, that calls a dispatch table entry.


