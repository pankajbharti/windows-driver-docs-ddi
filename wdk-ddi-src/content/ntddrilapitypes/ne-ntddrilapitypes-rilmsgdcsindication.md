---
UID: NE:ntddrilapitypes.RILMSGDCSINDICATION
title: RILMSGDCSINDICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsindication.htm
old-project: netvista
ms.assetid: 709980c8-e13f-48a7-9af7-26f0bb79e699
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilmsgdcsindication, RIL_DCSINDICATION_FAX, RILMSGDCSINDICATION enumeration [Network Drivers Starting with Windows Vista], RILMSGDCSINDICATION, ntddrilapitypes/RIL_DCSINDICATION_EMAIL, RIL_DCSINDICATION_EMAIL, ntddrilapitypes/RIL_DCSINDICATION_MAX, ntddrilapitypes/RILMSGDCSINDICATION, RIL_DCSINDICATION_OTHER, ntddrilapitypes/RIL_DCSINDICATION_FAX, RIL_DCSINDICATION_MAX, ntddrilapitypes/RIL_DCSINDICATION_OTHER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILMSGDCSINDICATION
product: Windows
targetos: Windows
req.typenames: RILMSGDCSINDICATION
---

# RILMSGDCSINDICATION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMSGDCSINDICATION { 
  RIL_DCSINDICATION_FAX,
  RIL_DCSINDICATION_EMAIL,
  RIL_DCSINDICATION_OTHER,
  RIL_DCSINDICATION_MAX
} RILMSGDCSINDICATION;
````


## -enum-fields




### -field RIL_DCSINDICATION_VOICEMAIL



### -field RIL_DCSINDICATION_FAX



### -field RIL_DCSINDICATION_EMAIL



### -field RIL_DCSINDICATION_OTHER



### -field RIL_DCSINDICATION_MAX


