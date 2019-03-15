---
UID: NF:ndis.NdisMQueueDpcEx
title: NdisMQueueDpcEx function (ndis.h)
description: NDIS miniport drivers call the NdisMQueueDpcEx function to schedule DPC calls on CPUs.
old-location: netvista\ndismqueuedpcex.htm
tech.root: netvista
ms.assetid: 22074e51-9032-4ef9-94b9-217daefcab03
ms.date: 05/02/2018
ms.keywords: NdisMQueueDpcEx, NdisMQueueDpcEx function [Network Drivers Starting with Windows Vista], ndis/NdisMQueueDpcEx, ndis_processor_group_ref_4a9c7d7e-69dd-4452-8e38-5234afb95f01.xml, netvista.ndismqueuedpcex
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMQueueDpcEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMQueueDpcEx function


## -description


NDIS miniport drivers call the 
  <b>NdisMQueueDpcEx</b> function to schedule DPC calls on CPUs.


## -parameters




### -param NdisInterruptHandle [in]

An interrupt handle that the miniport driver obtained in a previous call to the 
     <a href="https://msdn.microsoft.com/db0b3d51-5bbb-45fb-8c45-dda8c2212b5f">
     NdisMRegisterInterruptEx</a> function.


### -param MessageId [in]

An MSI message ID for the DPC. If the DPC is for a line-based interrupt, this parameter is not
     used and it should be set to zero. Otherwise, 
     <i>MessageId</i> is an index to the 
     <a href="https://msdn.microsoft.com/e5007381-2436-4eb6-85cd-7145361ab793">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structure inside a 
     <a href="https://msdn.microsoft.com/d740d55e-6549-494d-9b2a-39d5c2e670d3">
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
     <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> and 
     <a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">
     MiniportMessageInterruptDPC</a> functions.


## -returns



<b>NdisMQueueDpcEx</b> returns a bitmap that indicates target processors. Each bit in the return value
      identifies a CPU.

NDIS successfully scheduled a DPC for each target processor that is set in the bitmap. If NDIS sets
      bit 0, NDIS scheduled a DPC for CPU 0. If NDIS sets bit 1, NDIS scheduled a DPC for CPU 1, and so
      on.

If the driver requested a DPC for a CPU, and NDIS indicates that it did not schedule that DPC, then the DPC was not scheduled because the DPC that maps to this interrupt/processor pair was already scheduled for that CPU.




## -remarks



NDIS 6.20 and later miniport drivers call 
    <b>NdisMQueueDpcEx</b> to request DPC calls for other processors. NDIS calls the 
    <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> or 
    <a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">
    MiniportMessageInterruptDPC</a> function to complete the deferred processing of an interrupt.

<b>NdisMQueueDpcEx</b> is the same as the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563637">NdisMQueueDpc</a> function except that the 
    <i>TargetProcessors</i> parameter has a type of KGROUP_AFFINITY. Therefore, 
    <b>NdisMQueueDpcEx</b> can schedule DPCs on processors in any processor group. To schedule DPCs in more
    than one processor group, you can use multiple calls to 
    <b>NdisMQueueDpcEx</b>.

<div class="alert"><b>Note</b>  The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563637">NdisMQueueDpc</a>, 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>, and 
    <a href="https://msdn.microsoft.com/ec2e6f49-dc40-48e8-96dc-c9440a6662a3">
    MiniportMessageInterrupt</a> functions have a 
    <i>TargetProcessors</i> parameter that is a ULONG. This parameter specifies the first 32 processors in
    processor group 0.</div>
<div> </div>
<div class="alert"><b>Important</b>  NDIS 6.20 and later drivers should always use 
    <b>NdisMQueueDpcEx</b> to schedule DPCs.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/ec2e6f49-dc40-48e8-96dc-c9440a6662a3">MiniportMessageInterrupt</a>



<a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">MiniportMessageInterruptDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563637">NdisMQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a>
 

 

