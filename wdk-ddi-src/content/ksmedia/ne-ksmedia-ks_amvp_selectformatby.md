---
UID: NE:ksmedia.KS_AMVP_SELECTFORMATBY
title: KS_AMVP_SELECTFORMATBY
author: windows-driver-content
description: The KS_AMVP_SELECTFORMATBY enumeration specifies the criteria that the Overlay Mixer Filter should use to select the video format.
old-location: stream\ks_amvp_selectformatby.htm
old-project: stream
ms.assetid: b7fb6752-9711-4922-a806-915c362bcffe
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_AMVP_BEST_BANDWIDTH, KS_AMVP_SELECTFORMATBY enumeration [Streaming Media Devices], KS_AMVP_INPUT_SAME_AS_OUTPUT, KS_AMVP_DO_NOT_CARE, vidcapstruct_98fc9313-4177-46c2-8740-f0dc2857b447.xml, ksmedia/KS_AMVP_BEST_BANDWIDTH, ksmedia/KS_AMVP_INPUT_SAME_AS_OUTPUT, stream.ks_amvp_selectformatby, ksmedia/KS_AMVP_DO_NOT_CARE, KS_AMVP_SELECTFORMATBY, ksmedia/KS_AMVP_SELECTFORMATBY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname: 
-	KS_AMVP_SELECTFORMATBY
product: Windows
targetos: Windows
req.typenames: KS_AMVP_SELECTFORMATBY
---

# KS_AMVP_SELECTFORMATBY enumeration


## -description


The KS_AMVP_SELECTFORMATBY enumeration specifies the criteria that the Overlay Mixer Filter should use to select the video format.


## -syntax


````
typedef enum  { 
  KS_AMVP_DO_NOT_CARE           = 0,
  KS_AMVP_BEST_BANDWIDTH        = 1,
  KS_AMVP_INPUT_SAME_AS_OUTPUT  = 2
} KS_AMVP_SELECTFORMATBY;
````


## -enum-fields




### -field KS_AMVP_DO_NOT_CARE

The format does not matter.


### -field KS_AMVP_BEST_BANDWIDTH

Use the largest available bandwidth.


### -field KS_AMVP_INPUT_SAME_AS_OUTPUT

Use the same format for output as input.

