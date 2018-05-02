---
UID: NF:ndis.NdisAcquireRWLockRead
title: NdisAcquireRWLockRead function
author: windows-driver-content
description: The NdisAcquireRWLockRead function obtains a read lock that the caller uses for read access to resources that are shared among driver threads.
old-location: netvista\ndisacquirerwlockread.htm
old-project: netvista
ms.assetid: a9c16537-e344-43d4-bae7-fb11487caa0e
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisAcquireRWLockRead, NdisAcquireRWLockRead function [Network Drivers Starting with Windows Vista], ndis/NdisAcquireRWLockRead, ndis_processor_group_ref_0ac3bf44-b94f-4818-af69-79eec8045cc9.xml, netvista.ndisacquirerwlockread
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisAcquireRWLockRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAcquireRWLockRead function


## -description


The 
  <b>NdisAcquireRWLockRead</b> function obtains a read lock that the caller uses for read access to resources
  that are shared among driver threads.


## -parameters




### -param Lock [in]

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared between
     non-ISR driver threads.


### -param LockState [out]

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557070">LOCK_STATE_EX</a> variable that tracks the state
     of the lock. This variable exists in the interval between the times that the caller obtains and releases
     the lock. The caller must use a different variable of type <b>LOCK_STATE_EX</b> for each attempt that it makes
     to obtain the lock from the same non-ISR driver thread.


### -param Flags [in]

A <b>ULONG</b> value that contains lock flags. Set this parameter to <b>NDIS_RWL_AT_DISPATCH_LEVEL</b> if the
     caller's current IRQL is <b>DISPATCH_LEVEL</b>. Otherwise, set this parameter to zero. For more information
     about dispatch IRQL tracking, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.

<div class="alert"><b>Note</b>  If the caller knows the current IRQL is <b>DISPATCH_LEVEL</b>, set this parameter to <b>NDIS_RWL_AT_DISPATCH_LEVEL</b>.  This flag makes the lock even more efficient by causing it to omit a check for the current IRQL.  If the current IRQL is unknown, do not test the current IRQL with <a href="https://msdn.microsoft.com/library/windows/hardware/ff552054">KeGetCurrentIrql</a> solely to determine whether to set this flag, as it is more efficient to allow the <b>NdisAcquireRWLockRead</b> function to test the IRQL itself.</div>
<div> </div>

## -returns



None




## -remarks



NDIS drivers call the 
    <b>NdisAcquireRWLockRead</b> function to obtain read-only access to resources that are shared between
    driver threads.

The driver must allocate a variable of type 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561615">NdisAllocateRWLock</a> function before the
    driver calls the 
    <b>NdisAcquireRWLockRead</b> function.

After the driver calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561615">NdisAllocateRWLock</a>, it can call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a> or 
    <b>NdisAcquireRWLockRead</b> to obtain either write or read access to the resource. Only one non-ISR
    driver thread at a time can obtain write access to the resource. When one non-ISR thread has write
    access, all read and write accesses by other non-ISR threads must wait until the write-access holder
    releases the lock. However, if a non-ISR thread has read access, other non-ISR threads can concurrently
    obtain read access.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> lock does not support promotion from read to write.  Once a processor has acquired an <b>NDIS_RW_LOCK_EX</b> for read access (by calling <b>NdisAcquireRWLockRead</b>), the same processor must not attempt to acquire write access (by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a>) until the previous read access is released.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> read lock  can be acquired recursively on the same processor.  For each call to <b>NdisAcquireRWLockRead</b>, there must be a corresponding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a>.  The lock is only released after the last call to <b>NdisReleaseRWLock</b>.

The driver cannot use a lock to protect resources from read or write access that its other functions
    share with the 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> or 
    <a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">
    MiniportDisableInterruptEx</a> function, or both. Instead, the driver must call 
    <a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
    NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL that its 
    <i>MiniportInterrupt</i> or 
    <i>
    MiniportDisableInterruptEx</i> functions, or both do.

<b>NdisAcquireRWLockRead</b> always raises the IRQL to IRQL = <b>DISPATCH_LEVEL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557070">LOCK_STATE_EX</a>



<a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">MiniportDisableInterruptEx</a>



<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
   MiniportSynchronizeInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560698">NdisAcquireRWLockWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561615">NdisAllocateRWLock</a>



<a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a>
 

 

