---
UID: NF:ndis.NdisAllocateSpinLock
title: NdisAllocateSpinLock function
author: windows-driver-content
description: The NdisAllocateSpinLock function initializes a variable of type NDIS_SPIN_LOCK, used to synchronize access to resources shared among non-ISR driver functions.
old-location: netvista\ndisallocatespinlock.htm
old-project: netvista
ms.assetid: e6199eab-a1e8-428f-8a3c-4828d3899cec
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisallocatespinlock, NdisAllocateSpinLock, NdisAllocateSpinLock function [Network Drivers Starting with Windows Vista], ndis_spin_lock_ref_f42dc321-9805-443e-a7b3-315ab403aeba.xml, ndis/NdisAllocateSpinLock
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisAllocateSpinLock
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateSpinLock function


## -description


The 
  <b>NdisAllocateSpinLock</b> function initializes a variable of type NDIS_SPIN_LOCK, used to synchronize
  access to resources shared among non-ISR driver functions.


## -syntax


````
VOID NdisAllocateSpinLock(
  _Out_ PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters




### -param SpinLock [out]

Pointer to an opaque variable that represents a spin lock.


## -returns


None



## -remarks


Before a driver calls 
    <a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>, 
    <a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>, or any of
    the 
    <b>NdisInterlocked<i>Xxx</i></b> functions, it must call 
    <b>NdisAllocateSpinLock</b> to initialize the spin lock passed as a required parameter to these 
    <b>Ndis<i>Xxx</i></b> functions. The caller must provide nonpaged storage for the variable at 
    <i>SpinLock</i> .

After calling 
    <b>NdisAllocateSpinLock</b>, the driver can call 
    <b>NdisAcquireSpinLock</b> to obtain exclusive use of the resource(s) the spin lock protects. When
    resource access is complete, the driver calls 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a> so that other
    driver functions can access the resource(s) protected by that spin lock.

As a general rule, to improve performance a driver should use different locks to protect different
    critical sections. Thus, a driver might initialize more than one spin lock with 
    <b>NdisAllocateSpinLock</b>.

Each spin lock that a driver allocates protects a discrete set of shared resources from simultanous
    access by driver functions that run at IRQL &lt;= DISPATCH_LEVEL. For example, a driver that maintains an
    internal queue of packets might initialize one spin lock to protect its queue and another to protect a
    set of state variables that several driver functions, not including the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> or 
    <mshelp:link keywords="netvista.miniportdisableinterruptex" tabindex="0"><i>
    MiniportDisableInterruptEx</i></mshelp:link> function, access while the driver is processing packets.

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
</table></span></div>A driver should not access spin locks in this sequence for the following reasons:
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
</ul>A driver should 
    never use two spin locks to protect the same (sub)set of resources because nested spin lock
    acquisitions so frequently cause deadlocks. Even if a driver could be designed to prevent deadlocks,
    nested spin lock acquisitions have an adverse effect on driver performance and I/O throughput.

A miniport driver cannot use a spin lock to protect resources that its non-ISR functions share with
    its 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> or 
    <mshelp:link keywords="netvista.miniportdisableinterruptex" tabindex="0"><i>
    MiniportDisableInterruptEx</i></mshelp:link> function. To access resources shared with a 
    <i>MiniportInterrupt</i> or 
    <i>MiniportDisableInterruptEx</i> function, a miniport driver must call 
    <mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
    NdisMSynchronizeWithInterruptEx</b></mshelp:link> to have its 
    <mshelp:link keywords="netvista.miniportsynchronizeinterrupt" tabindex="0"><i>
    MiniportSynchronizeInterrupt</i></mshelp:link> function access those resources at DIRQL.

When a driver no longer requires resource protection, for example, when a NIC is being removed and the
    driver is releasing the resources it allocated for that NIC, the driver calls 
    <a href="..\ndis\nf-ndis-ndisfreespinlock.md">NdisFreeSpinLock</a>.

Freeing a spin lock and releasing a spin lock are potentially confusing. 
    <b>NdisFreeSpinLock</b> clears the memory at 
    <i>SpinLock</i> so it no longer represents a spin lock. Releasing an acquired spin lock with 
    <a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a> simply allows
    another thread of execution to acquire that spin lock.

For more information about acquiring and releasing NDIS spin locks, see 
    <mshelp:link keywords="netvista.synchronization_and_notification_in_network_drivers" tabindex="0">Synchronization
    and Notification in Network Drivers</mshelp:link>.

Callers of 
    <b>NdisAllocateSpinLock</b> can run at any IRQL. Usually a caller is running at IRQL = PASSIVE_LEVEL
    during initialization.



## -see-also

<mshelp:link keywords="netvista.driverentry_of_ndis_protocol_drivers" tabindex="0"><b>DriverEntry of NDIS Protocol
   Drivers</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>

<a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>

<a href="..\ndis\nf-ndis-ndisdpracquirespinlock.md">NdisDprAcquireSpinLock</a>

<mshelp:link keywords="netvista.ndisinterlockedinserttaillist" tabindex="0"><b>
   NdisInterlockedInsertTailList</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>

<mshelp:link keywords="netvista.ndismsynchronizewithinterruptex" tabindex="0"><b>
   NdisMSynchronizeWithInterruptEx</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>

<mshelp:link keywords="netvista.ndisinterlockedremoveheadlist" tabindex="0"><b>
   NdisInterlockedRemoveHeadList</b></mshelp:link>

<mshelp:link keywords="netvista.ndisinterlockedinsertheadlist" tabindex="0"><b>
   NdisInterlockedInsertHeadList</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisinterlockedaddulong.md">NdisInterlockedAddUlong</a>

<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>

<a href="..\ndis\nf-ndis-ndisfreespinlock.md">NdisFreeSpinLock</a>

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateSpinLock function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

