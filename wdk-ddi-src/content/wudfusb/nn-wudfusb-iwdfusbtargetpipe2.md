---
UID: NN:wudfusb.IWDFUsbTargetPipe2
title: IWDFUsbTargetPipe2
author: windows-driver-content
description: The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.
old-location: wdf\iwdfusbtargetpipe2.htm
old-project: wdf
ms.assetid: c3df39cb-17f4-4f68-bde3-f53ba40dde85
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfusbtargetpipe2, IWDFUsbTargetPipe2 interface, IWDFUsbTargetPipe2 interface, described, IWDFUsbTargetPipe2, wudfusb/IWDFUsbTargetPipe2, UMDFUSBref_835fc9c8-f01e-4b39-ab06-530f36886ea3.xml, umdf.iwdfusbtargetpipe2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfusb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	WUDFx.dll
apiname: 
-	IWDFUsbTargetPipe2
product: Windows
targetos: Windows
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.




## -members

The <b>IWDFUsbTargetPipe2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/accb2690-0ab7-4623-8493-545e6e722a7a">ConfigureContinuousReader</a> method configures the framework to continuously read from a USB pipe.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/accb2690-0ab7-4623-8493-545e6e722a7a">ConfigureContinuousReader</a> method configures the framework to continuously read from a USB pipe.

 


## -remarks


Drivers obtain the <b>IWDFUsbTargetPipe2</b> interface by calling <b>IWDFUsbTargetPipe::QueryInterface</b>.


