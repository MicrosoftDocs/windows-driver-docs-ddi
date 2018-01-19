---
UID: NF:ndis.NdisMQueueDpcEx
title: NdisMQueueDpcEx function
author: windows-driver-content
description: NDIS miniport drivers call the NdisMQueueDpcEx function to schedule DPC calls on CPUs.
old-location: netvista\ndismqueuedpcex.htm
old-project: netvista
ms.assetid: 22074e51-9032-4ef9-94b9-217daefcab03
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMQueueDpcEx
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
req.alt-api: NdisMQueueDpcEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMQueueDpcEx function



## -description
NDIS miniport drivers call the 
  <b>NdisMQueueDpcEx</b> function to schedule DPC calls on CPUs.



## -syntax

````
KAFFINITY NdisMQueueDpcEx(
  _In_ NDIS_HANDLE     NdisInterruptHandle,
  _In_ ULONG           MessageId,
  _In_ PGROUP_AFFINITY TargetProcessors,
  _In_ PVOID           MiniportDpcContext
);
````


## -parameters

### -param NdisInterruptHandle [in]

An interrupt handle that the miniport driver obtained in a previous call to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.


### -param MessageId [in]

An MSI message ID for the DPC. If the DPC is for a line-based interrupt, this parameter is not
     used and it should be set to zero. Otherwise, 
     <i>MessageId</i> is an index to the 
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info_entry.md">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structure inside a 
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.


### -param TargetProcessors [in]

A bitmap that indicates target processors. NDIS should schedule a DPC for each target processor
     that is indicated in the bitmap. Each bit in 
     <i>TargetProcessors</i> identifies a CPU. If the caller sets bit 0, NDIS schedules a DPC for CPU 0. If the caller sets bit 1, NDIS
     schedules a DPC for CPU 1, and so on.


### -param MiniportDpcContext [in]

A pointer to a caller-specified context area. NDIS passes this pointer to the 
     <i>MiniportDpcContext</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> and 
     <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
     MiniportMessageInterruptDPC</a> functions.


## -returns
<b>NdisMQueueDpcEx</b> returns a bitmap that indicates target processors. Each bit in the return value
      identifies a CPU.

NDIS successfully scheduled a DPC for each target processor that is set in the bitmap. If NDIS sets
      bit 0, NDIS scheduled a DPC for CPU 0. If NDIS sets bit 1, NDIS scheduled a DPC for CPU 1, and so
      on.

If the driver requested a DPC for a CPU, and NDIS indicates that it did not schedule that DPC, the
      DPC was not scheduled because a DPC was already scheduled for that CPU.


## -remarks
NDIS 6.20 and later miniport drivers call 
    <b>NdisMQueueDpcEx</b> to request DPC calls for other processors. NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> or 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
    MiniportMessageInterruptDPC</a> function to complete the deferred processing of an interrupt.

<b>NdisMQueueDpcEx</b> is the same as the 
    <a href="..\ndis\nf-ndis-ndismqueuedpc.md">NdisMQueueDpc</a> function except that the 
    <i>TargetProcessors</i> parameter has a type of KGROUP_AFFINITY. Therefore, 
    <b>NdisMQueueDpcEx</b> can schedule DPCs on processors in any processor group. To schedule DPCs in more
    than one processor group, you can use multiple calls to 
    <b>NdisMQueueDpcEx</b>.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismqueuedpc.md">NdisMQueueDpc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMQueueDpcEx function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

