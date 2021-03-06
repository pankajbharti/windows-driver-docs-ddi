---
UID: NS:rilapitypes.RILCBGWLCONFIGINFO
title: RILCBGWLCONFIGINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbgwlconfiginfo_2.htm
old-project: netvista
ms.assetid: 5939b967-bbc7-42e3-af90-a1c20698a934
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *LPRILCBGWLCONFIGINFO, netvista.rilcbgwlconfiginfo_2, rilapitypes/RILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	HeaderDef
apilocation: 
-	rilapitypes.h
apiname: 
-	RILCBGWLCONFIGINFO
product: Windows
targetos: Windows
req.typenames: RILCBGWLCONFIGINFO, *LPRILCBGWLCONFIGINFO
req.product: Windows 10 or later.
---

# RILCBGWLCONFIGINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCBGWLCONFIGINFO {
  BOOL      fAccept;
  RILRANGE  rgrrBroadcastMsgID;
} RILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO;
````


## -struct-fields




### -field fAccept



### -field rgrrBroadcastMsgID


