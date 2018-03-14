---
UID: NF:ndis.NdisMDeregisterInterruptEx
title: NdisMDeregisterInterruptEx function
author: windows-driver-content
description: Miniport drivers call NdisMDeregisterInterruptEx to release resources that were previously allocated with the NdisMRegisterInterruptEx function.
old-location: netvista\ndismderegisterinterruptex.htm
old-project: netvista
ms.assetid: bc0718b6-4c71-41a8-bab6-a52991b284d9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMDeregisterInterruptEx, NdisMDeregisterInterruptEx function [Network Drivers Starting with Windows Vista], ndis/NdisMDeregisterInterruptEx, ndis_interrupts_functions_ref_51574ad2-1b99-4238-b6a3-e427c321cd16.xml, netvista.ndismderegisterinterruptex
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
-	NdisMDeregisterInterruptEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMDeregisterInterruptEx function


## -description


Miniport drivers call 
  <b>NdisMDeregisterInterruptEx</b> to release resources that were previously allocated with the 
  <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
  NdisMRegisterInterruptEx</a> function.


## -syntax


````
VOID NdisMDeregisterInterruptEx(
  _In_ NDIS_HANDLE NdisInterruptHandle
);
````


## -parameters




### -param NdisInterruptHandle [in]

An interrupt handle that the miniport driver obtained in a previous call to 
     <b>NdisMRegisterInterruptEx</b>.


## -returns



None




## -remarks



<b>NdisMDeregisterInterruptEx</b> releases the resources that were allocated in 
    <b>NdisMRegisterInterruptEx</b>. After 
    <b>NdisMDeregisterInterruptEx</b> returns, NDIS will not call the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function or 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.

A miniport driver can call 
    <b>NdisMDeregisterInterruptEx</b> from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> or 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function only if 
    <i>MiniportInitializeEx</i> previously made a successful call to 
    <b>NdisMRegisterInterruptEx</b>.

The miniport driver should disable its NIC from generating interrupts before it calls 
    <b>NdisMDeregisterInterruptEx</b>. After 
    <b>NdisMDeregisterInterruptEx</b> returns control, the miniport driver cannot call the 
    <a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
    NdisMSynchronizeWithInterruptEx</a> function.




## -see-also

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
   NdisMSynchronizeWithInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInetrrupt</a>



 

 


