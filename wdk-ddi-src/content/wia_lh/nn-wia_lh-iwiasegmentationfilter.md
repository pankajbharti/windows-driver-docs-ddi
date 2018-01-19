---
UID: NN:wia_lh.IWiaSegmentationFilter
title: IWiaSegmentationFilter
author: windows-driver-content
description: The IWiaSegmentationFilter interface provides the DetectRegions method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.
old-location: image\iwiasegmentationfilter_interface.htm
old-project: image
ms.assetid: 93f2942b-3c01-43e7-9b8a-9542ab7bfd74
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IWiaTransferCallback, IWiaTransferCallback::TransferCallback, TransferCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wia_lh.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaSegmentationFilter
req.alt-loc: wia_lh.h
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
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaSegmentationFilter interface



## -description

The <b>IWiaSegmentationFilter</b> interface provides the <a href="https://msdn.microsoft.com/53ad769e-38b5-463d-9fa0-053c2215cc81">DetectRegions</a> method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.



The <b>IWiaSegmentationFilter</b> interface provides the <a href="https://msdn.microsoft.com/53ad769e-38b5-463d-9fa0-053c2215cc81">DetectRegions</a> method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaSegmentationFilter</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWiaSegmentationFilter</b> also has these types of members:

The <b>IWiaSegmentationFilter</b> interface has these methods.

The <b>IWiaSegmentationFilter::DetectRegions</b> method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item.

 


## -members
The <b>IWiaSegmentationFilter</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/53ad769e-38b5-463d-9fa0-053c2215cc81">DetectRegions</a>
</td>
<td align="left" width="63%">
The <b>IWiaSegmentationFilter::DetectRegions</b> method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item.

</td>
</tr>
</table>The <b>IWiaSegmentationFilter::DetectRegions</b> method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item.

 


## -remarks