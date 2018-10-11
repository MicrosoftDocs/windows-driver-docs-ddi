---
UID: NF:ndis.NdisAllocateSpinLock
title: NdisAllocateSpinLock function
author: windows-driver-content
description: The NdisAllocateSpinLock function initializes a variable of type NDIS_SPIN_LOCK, used to synchronize access to resources shared among non-ISR driver functions.
old-location: netvista\ndisallocatespinlock.htm
tech.root: netvista
ms.assetid: e6199eab-a1e8-428f-8a3c-4828d3899cec
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisAllocateSpinLock, NdisAllocateSpinLock function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateSpinLock, ndis_spin_lock_ref_f42dc321-9805-443e-a7b3-315ab403aeba.xml, netvista.ndisallocatespinlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisAllocateSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisAllocateSpinLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: SpinLockDpr, SpinLockDprRelease, SpinlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisAllocateSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateSpinLock function


## -description


The 
  <b>NdisAllocateSpinLock</b> function initializes a variable of type NDIS_SPIN_LOCK, used to synchronize
  access to resources shared among non-ISR driver functions.


## -parameters




### -param SpinLock [out]

Pointer to an opaque variable that represents a spin lock.


## -returns



None




## -remarks



Before a driver calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560699">NdisAcquireSpinLock</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561749">NdisDprAcquireSpinLock</a>, or any of
    the 
    <b>NdisInterlocked<i>Xxx</i></b> functions, it must call 
    <b>NdisAllocateSpinLock</b> to initialize the spin lock passed as a required parameter to these 
    <b>Ndis<i>Xxx</i></b> functions. The caller must provide nonpaged storage for the variable at 
    <i>SpinLock</i> .

After calling 
    <b>NdisAllocateSpinLock</b>, the driver can call 
    <b>NdisAcquireSpinLock</b> to obtain exclusive use of the resource(s) the spin lock protects. When
    resource access is complete, the driver calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a> so that other
    driver functions can access the resource(s) protected by that spin lock.

As a general rule, to improve performance a driver should use different locks to protect different
    critical sections. Thus, a driver might initialize more than one spin lock with 
    <b>NdisAllocateSpinLock</b>.

Each spin lock that a driver allocates protects a discrete set of shared resources from simultanous
    access by driver functions that run at IRQL &lt;= DISPATCH_LEVEL. For example, a driver that maintains an
    internal queue of packets might initialize one spin lock to protect its queue and another to protect a
    set of state variables that several driver functions, not including the 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> or 
    <a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">
    MiniportDisableInterruptEx</a> function, access while the driver is processing packets.

<b>NdisAcquireSpinLock</b> raises the IRQL to DISPATCH_LEVEL and stores the old IRQL in the spin lock.
    Releasing the spin lock sets the IRQL to the value stored in the spin lock. Because NDIS sometimes enters
    drivers at PASSIVE_LEVEL, problems can arise with the following code:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NdisAcquireSpinLock(A);
NdisAcquireSpinLock(B);
NdisReleaseSpinLock(A);
NdisReleaseSpinLock(B);</pre>
</td>
</tr>
</table></span></div>
A driver should not access spin locks in this sequence for the following reasons:

<ul>
<li>
Between 
      <b>NdisReleaseSpinLock</b>(A) and 
      <b>NdisReleaseSpinLock</b>(B) the code is running at PASSIVE_LEVEL instead of DISPATCH_LEVEL and is
      subject to inappropriate interruption.

</li>
<li>
After 
      <b>NdisReleaseSpinLock</b>(B) the code is running at DISPATCH_LEVEL which could cause the caller to
      fault at much later time with an IRQL_NOT_LESS_OR_EQUAL stop error.

</li>
</ul>
A driver should 
    never use two spin locks to protect the same (sub)set of resources because nested spin lock
    acquisitions so frequently cause deadlocks. Even if a driver could be designed to prevent deadlocks,
    nested spin lock acquisitions have an adverse effect on driver performance and I/O throughput.

A miniport driver cannot use a spin lock to protect resources that its non-ISR functions share with
    its 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> or 
    <a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">
    MiniportDisableInterruptEx</a> function. To access resources shared with a 
    <i>MiniportInterrupt</i> or 
    <i>MiniportDisableInterruptEx</i> function, a miniport driver must call 
    <a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
    NdisMSynchronizeWithInterruptEx</a> to have its 
    <a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
    MiniportSynchronizeInterrupt</a> function access those resources at DIRQL.

When a driver no longer requires resource protection, for example, when a NIC is being removed and the
    driver is releasing the resources it allocated for that NIC, the driver calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562602">NdisFreeSpinLock</a>.

Freeing a spin lock and releasing a spin lock are potentially confusing. 
    <b>NdisFreeSpinLock</b> clears the memory at 
    <i>SpinLock</i> so it no longer represents a spin lock. Releasing an acquired spin lock with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a> simply allows
    another thread of execution to acquire that spin lock.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.

Callers of 
    <b>NdisAllocateSpinLock</b> can run at any IRQL. Usually a caller is running at IRQL = PASSIVE_LEVEL
    during initialization.




## -see-also




<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">MiniportDisableInterruptEx</a>



<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560699">NdisAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561749">NdisDprAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561753">NdisDprReleaseSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562602">NdisFreeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562750">NdisInterlockedAddUlong</a>



<a href="https://msdn.microsoft.com/c6221ce9-682c-453b-b036-f4219c9540da">
   NdisInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/cc455bb1-3574-4dfb-9462-f2c67632132b">
   NdisInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/85cbc158-7132-4666-8161-a78251a62e4d">
   NdisInterlockedRemoveHeadList</a>



<a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a>



<a href="https://msdn.microsoft.com/76e59376-58a4-4e35-bac4-ec5938c88cd7">NetTimerCallback</a>
 

 

