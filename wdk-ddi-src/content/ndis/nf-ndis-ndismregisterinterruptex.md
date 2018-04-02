---
UID: NF:ndis.NdisMRegisterInterruptEx
title: NdisMRegisterInterruptEx function
author: windows-driver-content
description: NDIS miniport drivers call the NdisMRegisterInterruptEx function to register an interrupt.
old-location: netvista\ndismregisterinterruptex.htm
old-project: netvista
ms.assetid: db0b3d51-5bbb-45fb-8c45-dda8c2212b5f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMRegisterInterruptEx, NdisMRegisterInterruptEx function [Network Drivers Starting with Windows Vista], ndis/NdisMRegisterInterruptEx, ndis_interrupts_functions_ref_9a28602d-5a32-459c-92da-9d97b93f5fde.xml, netvista.ndismregisterinterruptex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Init_DeRegisterInterrupt, Init_RegisterInterrupt, Irql_Interrupt_Function, NdisMDeregisterInterruptEx
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMRegisterInterruptEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMRegisterInterruptEx function


## -description


NDIS miniport drivers call the 
  <b>NdisMRegisterInterruptEx</b> function to register an interrupt.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param MiniportInterruptContext [in]

A pointer to a block of context information. The miniport driver allocates this memory to store
     information about the interrupt. NDIS passes the context information block in subsequent calls to other
     functions that are associated with the interrupt.


### -param MiniportInterruptCharacteristics [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/f4176e2d-d8d2-4e75-bccb-0c452da4d703">
     NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a> structure that the miniport driver created. The driver
     initializes this structure with handler entry points and configuration parameters that define the
     interrupt characteristics.


### -param NdisInterruptHandle [out]

A pointer to an NDIS handle. NDIS writes the handle for the newly created interrupt object to the
     address that the 
     <i>NdisInterruptHandle</i> pointer specifies.


## -returns



<b>NdisMRegisterInterruptEx</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS initialized the interrupt object and supplied a valid interrupt handle at 
       <i>NdisInterruptHandle</i> . NDIS claimed hardware resources and set up the functions that it calls
       when an interrupt occurs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMRegisterInterruptEx</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i> or NT_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The attempt to initialize the interrupt object failed for reasons other than those in the
       preceding list.

</td>
</tr>
</table>
 




## -remarks



A miniport driver must call 
    <b>NdisMRegisterInterruptEx</b> from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function if
    it manages a NIC that generates interrupts.

<i>MiniportInitializeEx</i> must call the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function before calling 
    <b>NdisMRegisterInterruptEx</b>.

The miniport driver must specify entry points for the following interrupt service functions:


<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">
       MiniportDisableInterruptEx</a>



<a href="https://msdn.microsoft.com/61edeb80-a686-4b8c-ae19-4757616151ef">MiniportEnableInterruptEx</a>


If the NIC supports message-signaled interrupts (MSI), the miniport driver should specify entry points
    for the following MSI service functions:


<a href="https://msdn.microsoft.com/ec2e6f49-dc40-48e8-96dc-c9440a6662a3">MiniportMessageInterrupt</a>



<a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">
       MiniportMessageInterruptDPC</a>



<a href="https://msdn.microsoft.com/68d2076d-c991-4219-b6c3-2399ff5c11a3">
       MiniportDisableMessageInterrupt</a>



<a href="https://msdn.microsoft.com/b0e1bbef-8116-4455-aa5c-7f47386a3700">
       MiniportEnableMessageInterrupt</a>


If a driver specifies entry points for MSI, it must also specify entry points for the non-MSI
    interrupt service functions. Also, if 
    <b>NdisMRegisterInterruptEx</b> returns NDIS_STATUS_SUCCESS, the driver must examine the value of the 
    <b>InterruptType</b> member of the 
    <a href="https://msdn.microsoft.com/f4176e2d-d8d2-4e75-bccb-0c452da4d703">
    NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a> structure to determine the type of interrupts NDIS granted.
    If NDIS cannot grant MSI support, it will grant support for line based interrupts.

When interrupts are enabled on the NIC, a driver's 
    <i>MiniportInterrupt</i>(or 
    <i>MiniportMessageInterrupt</i>) function can be called at any time after the driver calls 
    <b>NdisMRegisterInterruptEx</b>, even before 
    <b>NdisMRegisterInterruptEx</b> returns. Therefore, a driver should not call 
    <b>NdisMRegisterInterruptEx</b> until it is ready to handle an interrupt.

Drivers call the 
    <a href="https://msdn.microsoft.com/bc0718b6-4c71-41a8-bab6-a52991b284d9">
    NdisMDeregisterInterruptEx</a> function to release resources that were previously allocated with 
    <b>NdisMRegisterInterruptEx</b>.




## -see-also




<a href="https://msdn.microsoft.com/6016ab15-56c6-4430-8883-d4cdcdf6116f">MiniportDisableInterruptEx</a>



<a href="https://msdn.microsoft.com/68d2076d-c991-4219-b6c3-2399ff5c11a3">
   MiniportDisableMessageInterrupt</a>



<a href="https://msdn.microsoft.com/61edeb80-a686-4b8c-ae19-4757616151ef">MiniportEnableInterruptEx</a>



<a href="https://msdn.microsoft.com/b0e1bbef-8116-4455-aa5c-7f47386a3700">
   MiniportEnableMessageInterrupt</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/ec2e6f49-dc40-48e8-96dc-c9440a6662a3">MiniportMessageInterrupt</a>



<a href="https://msdn.microsoft.com/c1eca20b-eda1-442c-8644-798fa864d5d7">MiniportMessageInterruptDPC</a>



<a href="https://msdn.microsoft.com/f4176e2d-d8d2-4e75-bccb-0c452da4d703">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563575">NdisMDeregisterInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
 

 

