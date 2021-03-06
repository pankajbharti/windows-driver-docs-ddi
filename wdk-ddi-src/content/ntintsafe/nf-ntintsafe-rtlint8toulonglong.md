---
UID: NF:ntintsafe.RtlInt8ToULongLong
title: RtlInt8ToULongLong function
author: windows-driver-content
description: Converts a value of type INT8 to a value of type ULONGLONG.
old-location: kernel\rtlint8toulonglong.htm
old-project: kernel
ms.assetid: C840CDA4-36C8-4D7C-88EB-19292429C45C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlInt8ToULongLong, RtlInt8ToULongLong function [Kernel-Mode Driver Architecture], kernel.rtlint8toulonglong, RtlInt8ToULongLong
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
-	RtlInt8ToULongLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlInt8ToULongLong function


## -description


Converts a value of type <b>INT8</b> to a value of type <b>ULONGLONG</b>.


## -syntax


````
NTSTATUS RtlInt8ToULongLong(
  _In_  INT8      i8Operand,
  _Out_ ULONGLONG *pullResult
);
````


## -parameters




### -param i8Operand [in]

The value to be converted.


### -param pullResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlInt8ToDWordLong</li>
<li>
RtlInt8ToULong64</li>
<li>
RtlInt8ToDWord64</li>
<li>
RtlInt8ToUInt64
</li>
</ul>

