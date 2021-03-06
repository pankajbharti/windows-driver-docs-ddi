---
UID: NF:ntintsafe.RtlLongLongToUShort
title: RtlLongLongToUShort function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type USHORT.
old-location: kernel\rtllonglongtoushort.htm
old-project: kernel
ms.assetid: 68D3A830-6687-4D45-8C9B-FC7B5E1F318A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongLongToUShort, kernel.rtllonglongtoushort, ntintsafe/RtlLongLongToUShort, RtlLongLongToUShort function [Kernel-Mode Driver Architecture]
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
-	RtlLongLongToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongLongToUShort function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>USHORT</b>.


## -syntax


````
NTSTATUS RtlLongLongToUShort(
  _In_  LONGLONG llOperand,
  _Out_ USHORT   *pusResult
);
````


## -parameters




### -param llOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>
RtlLongLongToUInt16
</li>
<li>RtlLongLongToWord
</li>
<li>RtlLong64ToUShort
</li>
<li>RtlLong64ToUInt16
</li>
<li>RtlLong64ToWord
</li>
<li>RtlInt64ToUShort
</li>
<li>RtlInt64ToUInt16
</li>
<li>RtlInt64ToWord
</li>
</ul>

