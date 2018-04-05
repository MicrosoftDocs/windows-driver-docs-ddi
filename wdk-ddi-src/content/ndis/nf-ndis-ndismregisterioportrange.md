---
UID: NF:ndis.NdisMRegisterIoPortRange
title: NdisMRegisterIoPortRange function
author: windows-driver-content
description: NdisMRegisterIoPortRange sets up driver access to device I/O ports with the NdisRawReadPortXxx and NdisRawWritePortXxx functions and claims the range of I/O port addresses in the registry for that driver's NIC.
old-location: netvista\ndismregisterioportrange.htm
old-project: netvista
ms.assetid: 3e7fc02b-9562-44b9-8659-793a1d96d1e9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMRegisterIoPortRange, NdisMRegisterIoPortRange function [Network Drivers Starting with Windows Vista], miniport_port_io_ref_fa0141f1-639d-485d-a074-8af029c04406.xml, ndis/NdisMRegisterIoPortRange, netvista.ndismregisterioportrange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMRegisterIoPortRange (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMRegisterIoPortRange (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMRegisterIoPortRange
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
-	NdisMRegisterIoPortRange
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMRegisterIoPortRange function


## -description


<b>NdisMRegisterIoPortRange</b> sets up driver access to device I/O ports with the 
  <b>NdisRawReadPort<i>Xxx</i></b> and 
  <b>NdisRawWritePort<i>Xxx</i></b> functions and claims the range of I/O port addresses in the registry for that driver's
  NIC.


## -parameters




### -param PortOffset [out]

Specifies a caller-supplied variable in which this function returns the mapped base virtual
     address for the given bus-relative I/O port range specified by 
     <i>InitialPort</i> and 
     <i>NumberOfPorts</i> .


### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param InitialPort [in]

Specifies the bus-relative base port address for a range of ports to be mapped.


### -param NumberOfPorts [in]

Specifies the number of ports in the range to be mapped.


## -returns



<b>NdisMRegisterIoPortRange</b> can return one of the following:

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
The given range of I/O ports was mapped successfully so the value at 
       <i>PortOffset</i> is valid and the mapped range has been claimed in the registry for the NIC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCE_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
An attempt to claim the I/O port range in the registry has failed, possibly because another
       driver already claimed the range for its device. 
       <b>NdisMRegisterIoPortRange</b> logs an error if this occurs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The port range could not be mapped or NDIS could not allocate resources to check the registry
       for hardware-resource conflicts.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
Either the bus type or bus number is out of range or the given 
       <i>InitialPort</i> and 
       <i>NumberOfPorts</i> were invalid (possibly not within the I/O port space of the current
       platform).

</td>
</tr>
</table>
 




## -remarks



A miniport driver calls 
    <b>NdisMRegisterIoPortRange</b> from its 
    <i>MiniportInitializeEx</i> function. 
    <i>MiniportInitializeEx</i> must call 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> before calling 
    <b>NdisMRegisterIoPortRange</b>.

<b>NdisMRegisterIoPortRange</b> maps a bus-relative device address range that the miniport driver can use
    subsequently to access an I/O port range on a NIC by calling the 
    <b>NdisRaw<i>Xxx</i></b> functions. A successful call claims the specified range of I/O ports in the registry for the
    caller's NIC.

Because the parameters passed to the 
    <b>NdisRaw<i>Xxx</i></b> have been mapped, these functions run significantly faster than the corresponding 
    <b>NdisImmediate..Port<i>Xxx</i></b>. After a successful call to 
    <b>NdisMRegisterIoPortRange</b>, a miniport driver cannot call any of the 
    <b>NdisImmediate..Port<i>Xxx</i></b> functions with either bus-relative addresses or mapped virtual addresses within such an I/O
    port range.

If its call to 
    <b>NdisMRegisterIoPortRange</b> fails, 
    <i>MiniportInitializeEx</i> should release all resources it already allocated for a NIC and, then, fail
    initialization for that NIC.

Drivers of NICs with device registers in the host memory space call 
    <b>NdisMMapIoSpace</b> and, subsequently, the 
    <b>NdisRead/WriteRegister<i>Xxx</i></b> functions to access the NIC registers.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563577">NdisMDeregisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563782">NdisRawReadPortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563785">NdisRawReadPortBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563791">NdisRawReadPortBufferUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563794">NdisRawReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563801">NdisRawReadPortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563808">NdisRawReadPortUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563811">NdisRawWritePortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563816">NdisRawWritePortBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563824">NdisRawWritePortBufferUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563829">NdisRawWritePortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563832">NdisRawWritePortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564510">NdisRawWritePortUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564513">NdisReadRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564514">NdisReadRegisterUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564515">NdisReadRegisterUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564678">NdisWriteRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564683">NdisWriteRegisterUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564685">NdisWriteRegisterUshort</a>
 

 

