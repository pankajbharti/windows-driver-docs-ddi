---
UID: NS:wditypes._WDI_CHANNEL_MAPPING_ENTRY
title: _WDI_CHANNEL_MAPPING_ENTRY
author: windows-driver-content
description: The WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry.
old-location: netvista\wdi_channel_mapping_entry.htm
old-project: netvista
ms.assetid: F05DAD5F-C0A4-46E0-8069-7CEF5B6C5707
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PWDI_CHANNEL_MAPPING_ENTRY, wditypes/PWDI_CHANNEL_MAPPING_ENTRY, wditypes/WDI_CHANNEL_MAPPING_ENTRY, netvista.wdi_channel_mapping_entry, PWDI_CHANNEL_MAPPING_ENTRY, WDI_CHANNEL_MAPPING_ENTRY structure [Device and Driver Installation], netvista.wifi_channel_mapping_entry, WDI_CHANNEL_MAPPING_ENTRY, _WDI_CHANNEL_MAPPING_ENTRY, PWDI_CHANNEL_MAPPING_ENTRY structure pointer [Device and Driver Installation]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wditypes.hpp
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
req.lib: 
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wditypes.hpp
apiname: 
-	WDI_CHANNEL_MAPPING_ENTRY
product: Windows
targetos: Windows
req.typenames: WDI_CHANNEL_MAPPING_ENTRY, *PWDI_CHANNEL_MAPPING_ENTRY
req.product: Windows 10 or later.
---

# _WDI_CHANNEL_MAPPING_ENTRY structure


## -description


The 
  WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry.


## -syntax


````
typedef struct _WDI_CHANNEL_MAPPING_ENTRY {
  UINT32 ChannelNumber;
  UINT32 ChannelCenterFrequency;
} WDI_CHANNEL_MAPPING_ENTRY, *PWDI_CHANNEL_MAPPING_ENTRY;
````


## -struct-fields




### -field ChannelNumber

Specifies the logical channel number.


### -field ChannelCenterFrequency

Specifies the center frequency for the channel in MHz.

