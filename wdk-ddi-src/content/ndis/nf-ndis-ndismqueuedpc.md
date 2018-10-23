---
UID: NF:ndis.NdisMQueueDpc
title: NdisMQueueDpc function
author: windows-driver-content
description: NDIS miniport drivers call the NdisMQueueDpc function to schedule DPC calls on CPUs.
old-location: netvista\ndismqueuedpc.htm
tech.root: netvista
ms.assetid: 203be18a-b3c5-420b-bcd1-1134beb1c8bd
ms.date: 05/02/2018
ms.keywords: NdisMQueueDpc, NdisMQueueDpc function [Network Drivers Starting with Windows Vista], ndis/NdisMQueueDpc, ndis_interrupts_functions_ref_a4b04210-b671-4ab3-8b5b-989bed907aed.xml, netvista.ndismqueuedpc
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NdisMQueueDpcEx.
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMQueueDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMQueueDpc function


## -description


NDIS miniport drivers call the 
  <b>NdisMQueueDpc</b> function to schedule DPC calls on CPUs.


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
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="https://msdn.microsoft.com/d740d55e-6549-494d-9b2a-39d5c2e670d3">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.


### -param TargetProcessors [in]

A bitmap that indicates the target processors for which NDIS should schedule a DPC. Each bit in 
     <i>TargetProcessors</i> identifies a CPU. If the caller sets bit 0, NDIS schedules a DPC for CPU 0. If the caller sets bit 1, NDIS
     schedules a DPC for CPU 1, and so forth.


### -param MiniportDpcContext [in, optional]

A pointer to a caller-specified context area. NDIS passes this pointer to the 
     <i>MiniportDpcContext</i> parameter of the 
     <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> and 
     <a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">
     MiniportMessageInterruptDPC</a> functions.


## -returns



<b>NdisMQueueDpc</b> returns a bitmap that indicates the target processors for which NDIS successfully
      scheduled a DPC. Each bit in the return value identifies a CPU. If NDIS sets bit 0, NDIS scheduled a DPC for CPU 0. If NDIS sets bit 1, NDIS scheduled a DPC
      for CPU 1, and so forth.

If the driver requested a DPC for a CPU, and NDIS indicates that it did not schedule that DPC, the
      DPC was not scheduled because a DPC was already scheduled for that CPU.




## -remarks



NDIS calls 
    <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> or 
    <a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">
    MiniportMessageInterruptDPC</a> to complete the deferred processing of an interrupt. The miniport
    driver can call 
    <b>NdisMQueueDpc</b> to request additional DPC calls for other processors.




## -see-also




<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">MiniportMessageInterruptDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563640">NdisMQueueDpcEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a>
 

 

