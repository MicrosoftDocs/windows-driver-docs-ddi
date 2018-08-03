---
UID: NF:ndis.NdisDeregisterProtocolDriver
title: NdisDeregisterProtocolDriver function
author: windows-driver-content
description: A protocol driver calls the NdisDeregisterProtocolDriver function to release the resources that NDIS allocated when the driver called the NdisRegisterProtocolDriver function.
old-location: netvista\ndisderegisterprotocoldriver.htm
tech.root: netvista
ms.assetid: 792f8f89-ff2c-45d1-bb15-9fcdafd14231
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisDeregisterProtocolDriver, NdisDeregisterProtocolDriver function [Network Drivers Starting with Windows Vista], ndis/NdisDeregisterProtocolDriver, netvista.ndisderegisterprotocoldriver, protocol_ndis_functions_ref_98dc25bb-4e04-42bb-a8b3-a997dcb77ac3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
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
-	NdisDeregisterProtocolDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisDeregisterProtocolDriver function


## -description


A protocol driver calls the
  <b>NdisDeregisterProtocolDriver</b> function to release the resources that NDIS allocated when the driver
  called the 
  <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
  NdisRegisterProtocolDriver</a> function.


## -parameters




### -param NdisProtocolHandle [in]

The handle returned by the 
     <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
     NdisRegisterProtocolDriver</a> function.


## -returns



None




## -remarks



Registered protocol drivers typically call 
    <b>NdisDeregisterProtocolDriver</b> when the driver's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine has been called or after errors occur
    in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. Protocol drivers must not
    call 
    <b>NdisDeregisterProtocolDriver</b> from any entry point that NDIS calls. Calling 
    <b>NdisDeregisterProtocolDriver</b> from such an entry point could cause a deadlock.

If a protocol driver has open bindings, its call to 
    <b>NdisDeregisterProtocolDriver</b> causes NDIS to call the protocol driver's 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function once for each open binding. NDIS calls 
    <i>ProtocolUnbindAdapterEx</i> within the context of the 
    <b>NdisDeregisterProtocolDriver</b> call.

After any outstanding bindings have been closed, 
    <b>NdisDeregisterProtocolDriver</b> releases all of the resources that NDIS allocated to track bindings
    and filters for the protocol driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a>
 

 

