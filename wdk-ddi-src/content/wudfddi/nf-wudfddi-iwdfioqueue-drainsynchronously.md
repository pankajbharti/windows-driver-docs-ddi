---
UID: NF:wudfddi.IWDFIoQueue.DrainSynchronously
title: IWDFIoQueue::DrainSynchronously method
author: windows-driver-content
description: The DrainSynchronously method directs the queue to reject new incoming I/O requests and allows already-queued requests to be delivered to the driver for processing. This method returns after all requests are completed or canceled.
old-location: wdf\iwdfioqueue_drainsynchronously.htm
old-project: wdf
ms.assetid: 6dc32dd7-e15b-4c93-92d1-5b7206ed98c0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfioqueue_drainsynchronously, IWDFIoQueue interface, DrainSynchronously method, DrainSynchronously method, IWDFIoQueue interface, umdf.iwdfioqueue_drainsynchronously, wudfddi/IWDFIoQueue::DrainSynchronously, IWDFIoQueue::DrainSynchronously, DrainSynchronously, IWDFIoQueue, UMDFQueueObjectRef_35105420-0461-4879-aba2-28c32ece9aab.xml, DrainSynchronously method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
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
-	IWDFIoQueue.DrainSynchronously
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::DrainSynchronously method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DrainSynchronously</b> method directs the queue to reject new incoming I/O requests and allows already-queued requests to be delivered to the driver for processing. This method returns after all requests are completed or canceled.


## -syntax


````
void  DrainSynchronously();
````


## -parameters





## -returns


None



## -remarks


The <b>DrainSynchronously</b> method is a synchronous version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a> method. That is, <b>DrainSynchronously</b> does not return to the driver until the queue is drained.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::DrainSynchronously method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

