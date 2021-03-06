---
UID: NF:ndis.NdisAcquireRWLockWrite
title: NdisAcquireRWLockWrite function
author: windows-driver-content
description: The NdisAcquireRWLockWrite function obtains a write lock that the caller uses for write access to resources that are shared between driver threads.
old-location: netvista\ndisacquirerwlockwrite.htm
old-project: netvista
ms.assetid: 124302d7-0776-4025-b71f-ce6300f97f49
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisacquirerwlockwrite, NdisAcquireRWLockWrite, NdisAcquireRWLockWrite function [Network Drivers Starting with Windows Vista], ndis_processor_group_ref_f957b48a-4c09-4348-897c-51813ede9b19.xml, ndis/NdisAcquireRWLockWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisAcquireRWLockWrite
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisAcquireRWLockWrite function


## -description


The 
  <b>NdisAcquireRWLockWrite</b> function obtains a write lock that the caller uses for write access to
  resources that are shared between driver threads.


## -syntax


````
VOID NdisAcquireRWLockWrite(
  _In_  PNDIS_RW_LOCK_EX Lock,
  _Out_ PLOCK_STATE_EX   LockState,
  _In_  UCHAR            Flags
);
````


## -parameters




### -param Lock [in]

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared between
     non-ISR driver threads.


### -param LockState [out]

A pointer to an opaque 
     <a href="..\ndis\ns-ndis-_lock_state_ex.md">LOCK_STATE_EX</a> variable that tracks the state
     of the lock. This variable exists in the interval between the times that the caller obtains and releases
     the lock. The caller must use a different variable of type <b>LOCK_STATE_EX</b> for each attempt that it makes to
     obtain the lock from the same non-ISR driver thread.


### -param Flags [in]

A <b>ULONG</b> value that contains lock flags. Set this parameter to <b>NDIS_RWL_AT_DISPATCH_LEVEL</b> if the
     caller's current IRQL is <b>DISPATCH_LEVEL</b>. Otherwise, set this parameter to zero. For more information
     about dispatch IRQL tracking, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.
<div class="alert"><b>Note</b>  If the caller knows the current IRQL is <b>DISPATCH_LEVEL</b>, set this parameter to <b>NDIS_RWL_AT_DISPATCH_LEVEL</b>.  This flag makes the lock even more efficient by causing it to omit a check for the current IRQL.  If the current IRQL is unknown, do not test the current IRQL with <a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a> solely to determine whether to set this flag, as it is more efficient to allow the <b>NdisAcquireRWLockWrite</b> function to test the IRQL itself.</div><div> </div>

## -returns


None



## -remarks


NDIS drivers call the 
    <b>NdisAcquireRWLockWrite</b> function to modify resources that are shared between driver threads.

The driver must allocate a variable of type 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> with the 
    <a href="..\ndis\nf-ndis-ndisallocaterwlock.md">NdisAllocateRWLock</a> function before the
    driver calls the 
    <b>NdisAcquireRWLockWrite</b> function. The driver must provide a handle to 
    <b>NdisAllocateRWLock</b> for the resident storage for the locks it uses.

After the driver calls 
    <a href="..\ndis\nf-ndis-ndisallocaterwlock.md">NdisAllocateRWLock</a>, it can call 
    <b>NdisAcquireRWLockWrite</b> or 
    <a href="..\ndis\nf-ndis-ndisacquirerwlockread.md">NdisAcquireRWLockRead</a> to obtain
    either write or read access to the resource. Only one non-ISR driver thread at a time can obtain write
    access to the resource. When one non-ISR thread has write access, all read and write accesses by other
    non-ISR threads must wait until the write-access holder releases the lock. However, if a non-ISR thread
    has read access, other non-ISR threads can concurrently obtain read access.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> lock does not support promotion from read to write.  Once a processor has acquired an <b>NDIS_RW_LOCK_EX</b> for read access (by calling <a href="..\ndis\nf-ndis-ndisacquirerwlockread.md">NdisAcquireRWLockRead</a>), the same processor must not attempt to acquire write access (by calling <b>NdisAcquireRWLockWrite</b>) until the previous read access is released.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> write lock  can be acquired recursively on the same processor.  For each call to <b>NdisAcquireRWLockWrite</b>, there must be a corresponding call to <a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a>.  The lock is only released after the last call to <b>NdisReleaseRWLock</b>.

A driver thread should never hold a write lock for more than a few microseconds. Holding a write lock
    for a prolonged period of time degrades both operating system and driver performance.

The driver cannot use a lock to protect resources from read or write access that its other functions
    share with the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> or 
    <mshelp:link keywords="netvista.miniportdisableinterruptex" tabindex="0"><i>
    MiniportDisableInterruptEx</i></mshelp:link> functions, or both. Instead, the driver must call 
    <mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
    NdisMSynchronizeWithInterruptEx</b></mshelp:link> so that its 
    <mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
    MiniportSynchronizeInterrupt</i></mshelp:link> function accesses such shared resources at the same DIRQL that its 
    <i>MiniportInterrupt</i> or 
    <i>
    MiniportDisableInterruptEx</i> functions, or both, do.

<b>NdisAcquireRWLockWrite</b> raises the IRQL to <b>DISPATCH_LEVEL</b> by obtaining a spin lock.



## -see-also

<mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
   NdisMSynchronizeWithInterruptEx</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisreleaserwlock.md">NdisReleaseRWLock</a>

<mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
   MiniportSynchronizeInterrupt</i></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>

<a href="..\ndis\nf-ndis-ndisallocaterwlock.md">NdisAllocateRWLock</a>

<a href="..\ndis\nf-ndis-ndisacquirerwlockread.md">NdisAcquireRWLockRead</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>

<a href="..\ndis\ns-ndis-_lock_state_ex.md">LOCK_STATE_EX</a>

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAcquireRWLockWrite function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

