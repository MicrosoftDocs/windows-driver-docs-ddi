---
UID: NF:ndis.NdisMRegisterDmaChannel
title: NdisMRegisterDmaChannel function (ndis.h)
description: The NdisMRegisterDmaChannel function claims a system DMA controller channel during initialization for DMA operations on a subordinate NIC or on an ISA bus-master NIC.
old-location: netvista\ndismregisterdmachannel.htm
tech.root: netvista
ms.assetid: 32e92f77-8f45-408b-a284-c00d3b5bd1b4
ms.date: 05/02/2018
keywords: ["NdisMRegisterDmaChannel function"]
ms.keywords: NdisMRegisterDmaChannel, NdisMRegisterDmaChannel function [Network Drivers Starting with Windows Vista], dma_ref_c0361623-95c8-4218-b848-8da949f22033.xml, ndis/NdisMRegisterDmaChannel, netvista.ndismregisterdmachannel
f1_keywords:
 - "ndis/NdisMRegisterDmaChannel"
 - "NdisMRegisterDmaChannel"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMRegisterDmaChannel (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMRegisterDmaChannel (NDIS   5.1)) in Windows XP.
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMRegisterDmaChannel
targetos: Windows
req.typenames: 
---

# NdisMRegisterDmaChannel function


## -description


The
  <b>NdisMRegisterDmaChannel</b> function claims a system DMA controller channel during initialization for DMA
  operations on a subordinate NIC or on an ISA bus-master NIC.


## -parameters




### -param MiniportDmaHandle [out]

A pointer to a caller-supplied variable in which this function returns a handle the miniport
     driver uses in subsequent calls to the 
     <b>NdisM<i>Xxx</i></b> system DMA functions.


### -param MiniportAdapterHandle [in]

The miniport adapter handle input to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param DmaChannel [in]

Ignored. Set the DMA channel, if any, at 
     <i>DmaDescription</i> .


### -param Dma32BitAddresses [in]

A boolean value that is <b>TRUE</b> if the NIC has 32 address lines. Otherwise, it is <b>FALSE</b>.


### -param DmaDescription [in]

A pointer to an NDIS_DMA_DESCRIPTION structure filled in by the caller. This structure is defined
     as follows: 
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _NDIS_DMA_DESCRIPTION {
    BOOLEAN DemandMode;
    BOOLEAN AutoInitialize;
    BOOLEAN DmaChannelSpecified;
    DMA_WIDTH DmaWidth;
    DMA_SPEED DmaSpeed;
    ULONG DmaPort;
    ULONG DmaChannel;
} NDIS_DMA_DESCRIPTION, *PNDIS_DMA_DESCRIPTION;</pre>
</td>
</tr>
</table></span></div>
The driver should initialize this structure with zeros before filling in the following members:





#### DemandMode

A boolean value that is <b>TRUE</b> if the subordinate NIC uses the system DMA controller's demand
       mode. Otherwise, it is <b>FALSE</b>.



#### AutoInitialize

A boolean value that is <b>TRUE</b> if the subordinate NIC uses the system DMA controller's
       autoinitialize mode. Otherwise, it is <b>FALSE</b>.



#### DmaChannelSpecified

A boolean value that is <b>TRUE</b> if 
       <b>DmaChannel</b> is set to the bus-relative value of the system DMA controller channel used by the
       NIC. Otherwise, it is <b>FALSE</b>.



#### DmaWidth

The transfer width for DMA operations, one of 
       <b>Width8Bits</b>, 
       <b>Width16Bits</b>, or 
       <b>Width32Bits</b>.



#### DmaSpeed

The DMA speed as one of 
       <b>Compatible</b>, 
       <b>TypeA</b>, 
       <b>TypeB</b>, or 
       <b>TypeC</b>.



#### DmaPort

This member refers to the MCA bus, which is no longer supported. This member must be
       zero.



#### DmaChannel

The bus-relative number of the system DMA controller channel used by the NIC.


### -param MaximumLength [in]

The maximum number of bytes that the NIC can transfer in a single DMA operation. If the NIC has
     unlimited transfer capacity, set this parameter to -1.


## -returns



<b>NdisMRegisterDmaChannel</b> can return one of the following status values:

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
NDIS claimed the specified DMA channel in the registry for the caller's NIC and set up necessary
       resources for subsequent DMA operations by the miniport driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCE_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
An attempt to claim the DMA channel in the registry has failed, possibly because another driver
       has already claimed that channel for its device. 
       <b>NdisMRegisterDmaChannel</b> logs an error if this occurs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not allocate the system resources it needs to support DMA operations by this miniport
       driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
Either the bus type or bus number is out of range or the driver declared the NIC to be a bus
       master on an I/O bus other than ISA.

</td>
</tr>
</table>
 




## -remarks



A driver of a subordinate-DMA NIC must call 
    <b>NdisMRegisterDmaChannel</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function to
    reserve system resources for subsequent DMA operations and to claim them in the registry.

The driver of an ISA bus-master NIC also must call 
    <b>NdisMRegisterDmaChannel</b> from 
    <i>MiniportInitializeEx</i> to claim a system DMA controller channel for the NIC in the registry.

<i>MiniportInitializeEx</i> must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function before calling 
    <b>NdisMRegisterDmaChannel</b>.

<i>MiniportInitializeEx</i> obtained the bus-relative values passed to 
    <b>NdisMRegisterDmaChannel</b> either from the registry or by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetbusdata">NdisMGetBusData</a> function.

If such a driver cannot allocate the system DMA resources that its device needs, 
    <i>MiniportInitializeEx</i> should release all resources it already allocated for the NIC and, then, fail
    initialization for that NIC.

If the driver successfully registers the DMA channel, it must later call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterdmachannel">
    NdisMDeregisterDmaChannel</a> function to deregister the DMA channel.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterdmachannel">NdisMDeregisterDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetbusdata">NdisMGetBusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

