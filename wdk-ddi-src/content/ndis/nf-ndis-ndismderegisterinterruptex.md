---
UID: NF:ndis.NdisMDeregisterInterruptEx
title: NdisMDeregisterInterruptEx function
author: windows-driver-content
description: Miniport drivers call NdisMDeregisterInterruptEx to release resources that were previously allocated with the NdisMRegisterInterruptEx function.
old-location: netvista\ndismderegisterinterruptex.htm
old-project: netvista
ms.assetid: bc0718b6-4c71-41a8-bab6-a52991b284d9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, E, I, M, N, NdisMDeregisterInterruptEx, NdisMDeregisterInterruptEx function [Network Drivers Starting with Windows Vista], d, e, g, i, n, ndis/NdisMDeregisterInterruptEx, ndis_interrupts_functions_ref_51574ad2-1b99-4238-b6a3-e427c321cd16.xml, netvista.ndismderegisterinterruptex, p, r, s, t, u, x"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
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



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
   NdisMSynchronizeWithInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInetrrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterInterruptEx function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

