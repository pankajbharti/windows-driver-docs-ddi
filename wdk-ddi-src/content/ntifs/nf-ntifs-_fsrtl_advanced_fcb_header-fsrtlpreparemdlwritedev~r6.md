---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPrepareMdlWriteDev~r6
title: FsRtlPrepareMdlWriteDev function
author: windows-driver-content
description: The FsRtlPrepareMdlWriteDev routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.
old-location: ifsk\fsrtlpreparemdlwritedev.htm
old-project: ifsk
ms.assetid: f425487d-c4cd-4fd0-93d3-d5ce15277c6d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/FsRtlPrepareMdlWriteDev, FsRtlPrepareMdlWriteDev routine [Installable File System Drivers], FsRtlPrepareMdlWriteDev, ifsk.fsrtlpreparemdlwritedev, fsrtlref_0d4bcdd2-9d31-41f1-aba3-ee9341d82b92.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	FsRtlPrepareMdlWriteDev
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlPrepareMdlWriteDev function


## -description


The <b>FsRtlPrepareMdlWriteDev</b> routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.


## -syntax


````
BOOLEAN FsRtlPrepareMdlWriteDev(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  ULONG            LockKey,
  _Out_ PMDL             *MdlChain,
  _Out_ PIO_STATUS_BLOCK IoStatus,
  _In_  PDEVICE_OBJECT   DeviceObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the file object.


### -param FileOffset [in]

A pointer to a value that specifies the starting byte offset within the cache that holds the data.


### -param Length [in]

The length in bytes of the data to read from the cache.


### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock. The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


### -param MdlChain [out]

On output, a pointer to a linked list of memory descriptor lists (MDLs) that point to the byte range within the cached data.


### -param IoStatus [out]

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


### -param DeviceObject [in]

The device object for the device that holds the file data.


## -returns


The <b>FsRtlPrepareMdlWriteDev</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.



## -remarks


<b>FsRtlPrepareMdlWriteDev</b> is similar to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite~r7.md">FsRtlCopyWrite</a>, except that <b>FsRtlPrepareMdlWriteDev </b>does not copy data to the cache. Instead, the physical pages that the caller will overwrite are locked in memory, and <b>FsRtlPrepareMdlWriteDev</b> returns one or more memory descriptor lists (MDLs) that point to the specified byte range. The locked pages remain locked until the caller calls <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlwritecompletedev~r3.md">FsRtlMdlWriteCompleteDev</a>. Thus each call to <b>FsRtlPrepareMdlWriteDev</b> must be followed by a call to <b>FsRtlMdlWriteCompleteDev</b>.

The pages that the MDLs point to are locked in memory, but are not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlwritecompletedev~r3.md">FsRtlMdlWriteCompleteDev</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite~r7.md">FsRtlCopyWrite</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlPrepareMdlWriteDev routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

