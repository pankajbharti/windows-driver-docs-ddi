---
UID: NS:ntddrilapitypes.RILCALLDISCONNECTDETAILS
title: RILCALLDISCONNECTDETAILS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetails.htm
old-project: netvista
ms.assetid: c933e219-47bb-4896-b5ee-bd2fd59f4e8c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcalldisconnectdetails, RILCALLDISCONNECTDETAILS, ntddrilapitypes/RILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS structure [Network Drivers Starting with Windows Vista], *LPRILCALLDISCONNECTDETAILS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname: 
-	RILCALLDISCONNECTDETAILS
product: Windows
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILS, *LPRILCALLDISCONNECTDETAILS
---

# RILCALLDISCONNECTDETAILS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCALLDISCONNECTDETAILS {
  RILCALLDISCONNECTDETAILSDISCONNECTGROUP  dwDisconnectGroup;
  NULL                                     RILCAUSEUNION;
  RILCAUSEUNION                            causeUnion;
  RILGPPCAUSE                              unGPPCause;
  RILGPPREJECTCAUSE                        unGPPRejectCause;
  RILGPP2CAUSE                             unGPP2Cause;
  RILIMSSIPCAUSE                           unIMSSIPCause;
  RILCALLDISCONNECTDETAILSASCODE           dwASCode;
  DWORD                                    dwOtherCode;
} RILCALLDISCONNECTDETAILS, RILCALLDISCONNECTDETAILS;
````


## -struct-fields




### -field causeUnion



### -field causeUnion.unGPPCause

 


### -field causeUnion.unGPPRejectCause

 


### -field causeUnion.unGPP2Cause

 


### -field causeUnion.unIMSSIPCause

 


### -field causeUnion.dwASCode

 


### -field causeUnion.dwOtherCode

 


### -field RILCAUSEUNION



### -field dwDisconnectGroup



#### - dwOtherCode



#### - dwASCode



#### - unGPPRejectCause



#### - unGPP2Cause



#### - unIMSSIPCause



#### - unGPPCause


