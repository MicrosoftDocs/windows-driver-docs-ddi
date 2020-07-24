---
UID: NF:ndis.NdisMSetupDmaTransfer
title: NdisMSetupDmaTransfer macro (ndis.h)
description: The NdisMSetupDmaTransfer function sets up the host DMA controller for a DMA transfer.
old-location: netvista\ndismsetupdmatransfer.htm
tech.root: netvista
ms.assetid: 2a7ebedd-0042-4624-9c9b-721cccfb0c4f
ms.date: 05/02/2018
keywords: ["NdisMSetupDmaTransfer macro"]
ms.keywords: NdisMSetupDmaTransfer, NdisMSetupDmaTransfer macro [Network Drivers Starting with Windows Vista], dma_ref_b6de5799-dca5-4c30-aa3a-e20e1eac4f0f.xml, ndis/NdisMSetupDmaTransfer, netvista.ndismsetupdmatransfer
f1_keywords:
 - "ndis/NdisMSetupDmaTransfer"
 - "NdisMSetupDmaTransfer"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMSetupDmaTransfer (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMSetupDmaTransfer (NDIS   5.1)) in Windows XP.
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
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMSetupDmaTransfer
targetos: Windows
req.typenames: 
---

# NdisMSetupDmaTransfer macro


## -description


The 
  <b>NdisMSetupDmaTransfer</b> function sets up the host DMA controller for a DMA transfer.


## -parameters




### -param _S

A pointer to a caller-supplied variable in which this function returns the status of the request,
     which can be one of the following:

#### NDIS_STATUS_SUCCESS

The DMA controller has been set up to transfer the specified data, which has been flushed to or
       from the device to maintain data integrity.



#### NDIS_STATUS_RESOURCES

An attempt to set up the DMA controller for the transfer has failed, either because the channel
       designated by 
       <i>MiniportDmaHandle</i> is currently in use transferring data or because the given 
       <i>Length</i> is invalid.


### -param _H

The DMA handle returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a> function
     during initialization.

### -param _B

A pointer to the buffer descriptor mapping the range of host memory from which or into which the
     data will be transferred.


### -param _O

The byte offset within the mapped buffer at which the transfer should start. Zero indicates the
     transfer should begin at the initial byte of the range specified at 
     <i>Buffer</i> .


### -param _L

The number of bytes of data to be transferred. The range specified by 
     <i>Offset</i> and 
     <i>Length</i> must be a proper subrange of that specified at 
     <i>Buffer</i> .


### -param _M_

A boolean value that is <b>TRUE</b> for an outbound transfer from the system through the NIC. Otherwise,
     it is <b>FALSE</b>.


## -remarks



Drivers of subordinate-DMA NICs call 
    <b>NdisMSetupDmaTransfer</b> in response to incoming send requests, for which the driver sets 
    <i>WriteToDevice</i> to <b>TRUE</b>. They set 
    <i>WriteToDevice</i> to <b>FALSE</b> when they transfer received data from the NIC to host memory.

The caller of 
    <b>NdisMSetupDmaTransfer</b> supplies a buffer descriptor mapping the host memory range that is the target
    of the transfer or that contains data for a download operation from the host to the NIC. To specify a
    transfer sized to suit the DMA constraints of the NIC, the caller can set up a subrange to be transferred
    with the 
    <i>Offset</i> and 
    <i>Length</i> parameters if necessary.

The caller must supply a buffer descriptor that specifies the host range into which received data will
    be transferred from the NIC when 
    <i>WriteToDevice</i> is <b>FALSE</b>. Otherwise, the buffer descriptor at 
    <i>Buffer</i> was chained to a packet descriptor input to the miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">
    MiniportSendNetBufferLists</a> function.

To improve performance for small transmit requests, such as a send request of less than 256 bytes in
    length, a miniport driver can copy the packet data into an internal staging buffer and pass a
    driver-allocated buffer descriptor mapping that buffer to 
    <b>NdisMSetupDmaTransfer</b>.

On return from 
    <b>NdisMSetupDmaTransfer</b>, the host DMA controller has been programmed for the transfer. The miniport
    driver then programs the NIC for the transfer operation.

When the transfer is complete, the miniport driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcompletedmatransfer">
    NdisMCompleteDmaTransfer</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">MiniportSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcompletedmatransfer">NdisMCompleteDmaTransfer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a>
 

 

