---
UID: NF:video._VIDEO_PORT_DEBUG_REPORT_INTERFACE.BOOLEAN
title: BOOLEAN function (video.h)
description: Miniport drivers call the NdisMSynchronizeWithInterruptEx function to synchronize the execution of a miniport driver-supplied function with the MiniportInterrupt function.
old-location: netvista\ndismsynchronizewithinterruptex.htm
tech.root: netvista
ms.assetid: 5dca9258-a3ae-43f4-a5aa-d591165d72ed
ms.date: 02/27/2018
ms.keywords: BOOLEAN, NdisMSynchronizeWithInterruptEx, NdisMSynchronizeWithInterruptEx function [Network Drivers Starting with Windows Vista], ndis/NdisMSynchronizeWithInterruptEx, ndis_interrupts_functions_ref_e2b886ed-7425-4f7e-8cb6-4e3946dec8ff.xml, netvista.ndismsynchronizewithinterruptex
ms.topic: function
f1_keywords:
 - "video/NdisMSynchronizeWithInterruptEx"
req.header: video.h
req.include-header: Ndis.h, Video.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance: NdisMDeregisterInterruptEx
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib: Ndis.lib
req.dll:
req.irql: <= DIRQL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMSynchronizeWithInterruptEx
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# BOOLEAN function


## -description


Miniport drivers call the
  <b>NdisMSynchronizeWithInterruptEx</b> function to synchronize the execution of a miniport driver-supplied
  function with the
  <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function.


## -syntax


```cpp
BOOLEAN NdisMSynchronizeWithInterruptEx(
  _In_ NDIS_HANDLE NdisInterruptHandle,
  _In_ ULONG       MessageId,
  _In_ PVOID       SynchronizeFunction,
  _In_ PVOID       SynchronizeContext
);
```


## -parameters




### -param NdisInterruptHandle 

[in] An interrupt handle that the miniport driver obtained in a previous call to the <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function.

<p>An interrupt handle that the miniport driver obtained in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex"><b>NdisMRegisterInterruptEx</b></a> function.</p>




### -param MessageId 

[in] A message-signaled interrupt with which the driver must synchronize. If NDIS did not grant message signaled interrupts for the driver, NDIS ignores this parameter.
     <i>MessageId</i> is an index to the
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info_entry.md">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the
     <b>NdisMRegisterInterruptEx</b> function.


### -param SynchronizeFunction 

[in] The entry point of the driver's
     <a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
     MiniportSynchronizeInterrupt</a> function.

### -param SynchronizeContext 

[in] A pointer to a miniport-driver-determined context area that is passed to the
     <i>MiniportSynchronizeInterrupt</i> function at
     <i>SynchronizeContext</i> .





## -returns



<b>NdisMSynchronizeWithInterruptEx</b> returns the Boolean value that
     <i>MiniportSynchronizeInterrupt</i> returns.




## -remarks



Miniport drivers that register an interrupt with
    <b>NdisMRegisterInterruptEx</b> use
    <b>NdisMSynchronizeWithInterruptEx</b>. The value that the
    <a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
    MiniportSynchronizeInterrupt</a> function returns is also returned by
    <b>NdisMSynchronizeWithInterruptEx</b>. This propagated value provides status to the caller.

Any miniport driver function that shares resources with any other driver function that runs at DIRQL
    must use
    <b>NdisMSynchronizeWithInterruptEx</b> to synchronize its access to those resources. The
    <i>MiniportSynchronizeInterrupt</i> function also runs at DIRQL, and the shared resources are protected by
    a system-allocated spin lock. Thus, the shared resources are protected from simultaneous access by the
    <i>MiniportInterrupt</i> function and the caller.

<b>NdisMSynchronizeWithInterruptEx</b> releases the system spin lock and restores the original IRQL of its
    caller before it returns control.

For more information about acquiring and releasing NDIS spin locks, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.




## -see-also

<a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
   MiniportSynchronizeInterrupt</a>



<a href="..\wdm\ns-wdm-_io_interrupt_message_info_entry.md">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>



 

 


