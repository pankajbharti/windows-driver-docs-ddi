---
UID: NF:ntintsafe.RtlLongToULongPtr
title: RtlLongToULongPtr function
author: windows-driver-content
description: Converts a value of type LONG to a value of type ULONG_PTR.
old-location: kernel\rtllongtoulongptr.htm
old-project: kernel
ms.assetid: D05EDC76-7A3E-4A9F-8950-8E54CDD16016
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlLongToULongPtr, kernel.rtllongtoulongptr, RtlLongToULongPtr function [Kernel-Mode Driver Architecture], RtlLongToULongPtr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntintsafe.h
apiname: 
-	RtlLongToULongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToULongPtr function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>ULONG_PTR</b>.


## -syntax


````
NTSTATUS RtlLongToULongPtr(
  _In_  LONG      ulOperand,
  _Out_ ULONG_PTR *pusResult
);
````


## -parameters




### -param lOperand

TBD


### -param pulResult

TBD



#### - ulOperand [in]

The value to be converted.


#### - pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlLongToDWordPtr
</li>
<li>RtlLongToSIZET
</li>
</ul>

