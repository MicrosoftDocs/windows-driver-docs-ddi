---
UID: NF:ndis.NdisMDeregisterInterruptEx
title: NdisMDeregisterInterruptEx function
description: Miniport drivers call NdisMDeregisterInterruptEx to release resources that were previously allocated with the NdisMRegisterInterruptEx function.
old-location: netvista\ndismderegisterinterruptex.htm
tech.root: netvista
ms.assetid: bc0718b6-4c71-41a8-bab6-a52991b284d9
ms.date: 05/02/2018
ms.keywords: NdisMDeregisterInterruptEx, NdisMDeregisterInterruptEx function [Network Drivers Starting with Windows Vista], ndis/NdisMDeregisterInterruptEx, ndis_interrupts_functions_ref_51574ad2-1b99-4238-b6a3-e427c321cd16.xml, netvista.ndismderegisterinterruptex
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMDeregisterInterruptEx function


## -description


Miniport drivers call 
  <b>NdisMDeregisterInterruptEx</b> to release resources that were previously allocated with the 
  <a href="https://msdn.microsoft.com/db0b3d51-5bbb-45fb-8c45-dda8c2212b5f">
  NdisMRegisterInterruptEx</a> function.


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
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> function or 
    <a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a> function.

A miniport driver can call 
    <b>NdisMDeregisterInterruptEx</b> from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> or 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function only if 
    <i>MiniportInitializeEx</i> previously made a successful call to 
    <b>NdisMRegisterInterruptEx</b>.

The miniport driver should disable its NIC from generating interrupts before it calls 
    <b>NdisMDeregisterInterruptEx</b>. After 
    <b>NdisMDeregisterInterruptEx</b> returns control, the miniport driver cannot call the 
    <a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
    NdisMSynchronizeWithInterruptEx</a> function.




## -see-also




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInetrrupt</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a>



<a href="https://msdn.microsoft.com/5dca9258-a3ae-43f4-a5aa-d591165d72ed">
   NdisMSynchronizeWithInterruptEx</a>
 

 

