---
UID: NF:wdfrequest.WdfRequestMarkCancelableEx
title: WdfRequestMarkCancelableEx function
author: windows-driver-content
description: The WdfRequestMarkCancelableEx method enables cancellation of a specified I/O request.
old-location: wdf\wdfrequestmarkcancelableex.htm
old-project: wdf
ms.assetid: 5513804b-f785-4617-81b6-1cecc72d6051
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFRequestObjectRef_6601e5df-d8a6-42b5-9e71-a46918a6bc1f.xml, PFN_WDFREQUESTMARKCANCELABLEEX, kmdf.wdfrequestmarkcancelableex, WdfRequestMarkCancelableEx, wdf.wdfrequestmarkcancelableex, wdfrequest/WdfRequestMarkCancelableEx, WdfRequestMarkCancelableEx method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 2.0
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname: 
-	WdfRequestMarkCancelableEx
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestMarkCancelableEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestMarkCancelableEx</b> method enables cancellation of a specified I/O request.


## -syntax


````
NTSTATUS WdfRequestMarkCancelableEx(
  _In_ WDFREQUEST             Request,
  _In_ PFN_WDF_REQUEST_CANCEL EvtRequestCancel
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param EvtRequestCancel [in]

A pointer to a driver-defined <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function, which the framework calls if it cancels the I/O request.


## -returns


<b>WdfRequestMarkCancelableEx</b> returns STATUS_SUCCESS if it successfully enables cancellation of the specified I/O request. Otherwise, this method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request has been canceled. See Remarks for more info.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
<ul>
<li>
The driver does not own the I/O request.

</li>
<li>
The I/O request is already cancelable.

</li>
</ul>
</td>
</tr>
</table> 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


After your driver has <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/receiving-i-o-requests">received an I/O request</a> from the framework, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or, starting with  KMDF version 1.9, <b>WdfRequestMarkCancelableEx</b> to make the request cancelable. For info on choosing between the two methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a>.

When calling <b>WdfRequestMarkCancelableEx</b>, your driver must specify an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.

If <b>WdfRequestMarkCancelableEx</b> returns failure, the driver must perform the same cancellation activities that the <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function performs.  For example:
<ol>
<li>
Finish or stop processing the request, along with subrequests that it might have created.

</li>
<li>
Call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>, specifying a status value of STATUS_CANCELLED.

</li>
</ol> See the code examples below for implementation.

Because <b>WdfRequestMarkCancelableEx</b> never calls <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>, this method is safe from the deadlock risk described in the Remarks of <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>.
<h3><a id="Processing_a_request_after_enabling_cancellation"></a><a id="processing_a_request_after_enabling_cancellation"></a><a id="PROCESSING_A_REQUEST_AFTER_ENABLING_CANCELLATION"></a>Processing a request after enabling cancellation</h3>After a driver calls <b>WdfRequestMarkCancelableEx</b> to enable canceling, the request remains cancelable while the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request object, unless the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>. 

If a driver has called <b>WdfRequestMarkCancelableEx</b>, and if the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function has not executed and called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.

If the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:
<ul>
<li>
I/O requests cannot be cancelable when your driver forwards them to a different queue. 

Generally, your driver should not call <b>WdfRequestMarkCancelableEx</b> to enable canceling the request before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.

</li>
<li>
While the request is in the second queue, the framework owns it and can cancel it without notifying the driver. 

If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue.md">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.

</li>
<li>
After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelableEx</b> to enable canceling.

</li>
</ul>For more information about <b>WdfRequestMarkCancelableEx</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>

<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestMarkCancelableEx method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

