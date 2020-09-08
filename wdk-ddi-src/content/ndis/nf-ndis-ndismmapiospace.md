---
UID: NF:ndis.NdisMMapIoSpace
title: NdisMMapIoSpace function (ndis.h)
description: NdisMMapIoSpace maps a given bus-relative &#0034;physical&#0034; range of device RAM or registers onto a system-space virtual range.
old-location: netvista\ndismmapiospace.htm
tech.root: netvista
ms.assetid: 16c62146-ed8d-4bf7-9d5e-0c5dbbf3c9c4
ms.date: 05/02/2018
keywords: ["NdisMMapIoSpace function"]
ms.keywords: NdisMMapIoSpace, NdisMMapIoSpace function [Network Drivers Starting with Windows Vista], miniport_memory_mapped_ref_b346fbc3-62d5-447e-82af-329afbafdb73.xml, ndis/NdisMMapIoSpace, netvista.ndismmapiospace
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMMapIoSpace (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMMapIoSpace (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMMapIoSpace
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMMapIoSpace
 - ndis/NdisMMapIoSpace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMMapIoSpace
---

# NdisMMapIoSpace function


## -description

<b>NdisMMapIoSpace</b> maps a given bus-relative "physical" range of device RAM or registers onto a
  system-space virtual range.

## -parameters

### -param VirtualAddress 

[out]
Pointer to a caller-supplied variable that is set to the converted virtual address if the call is
     successful.

### -param MiniportAdapterHandle 

[in]
Specifies the handle input to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.

### -param PhysicalAddress 

[in]
Specifies the bus-relative base physical address of the device memory range to be mapped.

### -param Length 

[in]
Specifies the number of bytes to be mapped.

## -returns

<b>NdisMMapIoSpace</b> can return any of the following status values:

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
The device memory range was mapped successfully so the value at 
       <i>VirtualAddress</i> is valid and the mapped range has been claimed in the registry for the
       NIC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCE_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
An attempt to claim the device memory range in the registry has failed, possibly because another
       driver has already claimed the range for its device. 
       <b>NdisMMapIoSpace</b> logs an error if this occurs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The memory could not be mapped or sufficient virtual memory could not be allocated.

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
       <i>PhysicalAddress</i> and 
       <i>Length</i> were invalid (possibly not within the I/O space of the current platform).

</td>
</tr>
</table>

## -remarks

This function is called by drivers of NICs that have on-board memory or a bank of device registers
    appearing in the I/O space of the host. For example, the driver of a NIC that uses PIO calls 
    <b>NdisMMapIoSpace</b>.

A successful call to 
    <b>NdisMMapIoSpace</b> claims hardware resources in the registry for the driver's NIC. Consequently, only 
    <i>MiniportInitializeEx</i> functions call 
    <b>NdisMMapIoSpace</b>.

<b>NdisMMapIoSpace</b> sets the variable at 
    <i>VirtualAddress</i> to <b>NULL</b> if it does not return NDIS_STATUS_SUCCESS.

MiniportInitializeEx either gets the 
    <i>PhysicalAddress</i> value from the driver's 
    <b>Parameters</b> registry key or by calling a bus-type-specific 
    <b>Ndis<i>Xxx</i></b> configuration function. The given physical address range must fall within the I/O space of the
    current platform. It is a programming error to call 
    <b>NdisMMapIoSpace</b> with a host physical memory address.

A miniport driver must call the reciprocal 
    <b>NdisMUnmapIoSpace</b> to release its claim on system resources if 
    <i>MiniportInitializeEx</i> subsequently fails to initialize a NIC, if a NIC is removed from the machine,
    and/or when the driver is unloading.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetbusdata">NdisMGetBusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismunmapiospace">NdisMUnmapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisteruchar">NdisReadRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisterulong">NdisReadRegisterUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisterushort">NdisReadRegisterUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisteruchar">NdisWriteRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisterulong">NdisWriteRegisterUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisterushort">NdisWriteRegisterUshort</a>

