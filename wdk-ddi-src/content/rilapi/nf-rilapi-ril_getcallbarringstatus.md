---
UID: NF:rilapi.RIL_GetCallBarringStatus
title: RIL_GetCallBarringStatus function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getcallbarringstatus.htm
old-project: netvista
ms.assetid: 403e17c1-1353-42dd-aedc-8aec1fd72e0f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_getcallbarringstatus, rilapi/RIL_GetCallBarringStatus, RIL_GetCallBarringStatus, RIL_GetCallBarringStatus method [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	rilapi.h
apiname: 
-	RIL_GetCallBarringStatus
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetCallBarringStatus function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetCallBarringStatus(
   HRIL                           hRil,
   LPVOID                         lpContext,
   DWORD                          dwExecutor,
   RILCALLBARRINGSTATUSPARAMSTYPE dwType,
   BOOL                           fAllClasses,
   DWORD                          dwInfoClasses
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwExecutor



### -param dwType



### -param fAllClasses



### -param dwInfoClasses



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


