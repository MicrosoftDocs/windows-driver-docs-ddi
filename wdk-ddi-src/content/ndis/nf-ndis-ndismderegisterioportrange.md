---
UID: NF:ndis.NdisMDeregisterIoPortRange
title: NdisMDeregisterIoPortRange function
author: windows-driver-content
description: NdisMDeregisterIoPortRange releases a mapping that was set up with NdisMRegisterIoPortRange during driver initialization.
old-location: netvista\ndismderegisterioportrange.htm
tech.root: netvista
ms.assetid: b5b6a608-af1f-4030-b83a-a6f64ff3a264
ms.date: 05/02/2018
ms.keywords: NdisMDeregisterIoPortRange, NdisMDeregisterIoPortRange function [Network Drivers Starting with Windows Vista], miniport_port_io_ref_3ec72b06-3f52-46b9-b699-774a7df4a658.xml, ndis/NdisMDeregisterIoPortRange, netvista.ndismderegisterioportrange
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMDeregisterIoPortRange   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMDeregisterIoPortRange   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
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
-	NdisMDeregisterIoPortRange
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMDeregisterIoPortRange function


## -description


<b>NdisMDeregisterIoPortRange</b> releases a mapping that was set up with 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a> during
  driver initialization.


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param InitialPort [in]

Specifies the bus-relative address of the first port in the range of ports.


### -param NumberOfPorts [in]

Specifies the number of ports in the range.


### -param PortOffset [in]

Specifies the mapped base port address returned by 
     <b>NdisMRegisterIoPortRange</b>.


## -returns



None




## -remarks



The miniport driver must pass the same 
    <i>InitialPort</i> and 
    <i>NumberOfPorts</i> to 
    <b>NdisMDeregisterIoPortRange</b> that were passed when 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a> to get
    the mapped 
    <i>PortOffset</i> value. That is, a miniport driver cannot call 
    <b>NdisMDeregisterIoPortRange</b> to release a subrange of a mapped port range.

<b>NdisMDeregisterIoPortRange</b> can be called from the 
    <i>MiniportInitializeEx</i> or 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> functions only if 
    <i>MiniportInitializeEx</i> previously made a successful call to 
    <b>NdisMRegisterIoPortRange</b>.

<b>NdisMDeregisterIoPortRange</b> also releases the driver's claim on the I/O port range in the
    registry.

After it calls 
    <b>NdisMRegisterIoPortRange</b>, the miniport driver can no longer access the NIC's port range with calls
    to the 
    <b>NdisRaw..Port<i>Xxx</i></b> functions.




## -see-also




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>
 

 

