---
UID: NS:rilapitypes.RILOPERATORINFO
title: RILOPERATORINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riloperatorinfo_2.htm
old-project: netvista
ms.assetid: cf189a5a-8281-4d9a-bad8-a25a1294aec9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.riloperatorinfo_2, RILOPERATORINFO structure [Network Drivers Starting with Windows Vista], RILOPERATORINFO, rilapitypes/RILOPERATORINFO, *LPRILOPERATORINFO
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
-	RILOPERATORINFO
product: Windows
targetos: Windows
req.typenames: *LPRILOPERATORINFO, RILOPERATORINFO
req.product: Windows 10 or later.
---

# RILOPERATORINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILOPERATORINFO {
  DWORD                  cbSize;
  DWORD                  dwParams;
  DWORD                  dwIndex;
  RILOPERATORINFOSTATUS  dwStatus;
  RILOPERATORNAMES       ronNames;
} RILOPERATORINFO, RILOPERATORINFO;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwIndex



### -field dwStatus



### -field ronNames


