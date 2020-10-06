---
UID: NF:ndis.NdisMCompleteDmaTransfer
title: NdisMCompleteDmaTransfer macro (ndis.h)
description: The NdisMCompleteDmaTransfer function indicates that a system DMA transfer operation has completed. It resets the system DMA controller in preparation for further DMA transfers.
old-location: netvista\ndismcompletedmatransfer.htm
tech.root: netvista
ms.assetid: 12a8062a-6d4b-4757-a076-56aeb5e4e48c
ms.date: 05/02/2018
keywords: ["NdisMCompleteDmaTransfer macro"]
ms.keywords: NdisMCompleteDmaTransfer, NdisMCompleteDmaTransfer macro [Network Drivers Starting with Windows Vista], dma_ref_bd601fef-cf06-42ff-9906-d3bf8edef72f.xml, ndis/NdisMCompleteDmaTransfer, netvista.ndismcompletedmatransfer
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCompleteDmaTransfer (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCompleteDmaTransfer (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCompleteDmaTransfer
 - ndis/NdisMCompleteDmaTransfer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMCompleteDmaTransfer
---

# NdisMCompleteDmaTransfer macro


## -description

The 
  <b>NdisMCompleteDmaTransfer</b> function indicates that a system DMA transfer operation has completed. It
  resets the system DMA controller in preparation for further DMA transfers.

## -parameters

### -param _S

A pointer to a caller-supplied variable in which this function returns the final status of the DMA
     transfer, which can be one of the following:

#### NDIS_STATUS_SUCCESS

The data has been transferred and flushed to host memory or to the device to maintain data
       integrity.


#### NDIS_STATUS_RESOURCES

The DMA controller was released but the data transfer might be incoherent.

### -param _H

The handle returned when the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
     called the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">
     NdisMRegisterDmaChannel</a> function.

### -param _B

A pointer to the buffer descriptor previously passed to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetupdmatransfer">NdisMSetupDmaTransfer</a>.

### -param _O

The byte offset at which the transfer began. This value also was passed to 
     <b>NdisMSetupDmaTransfer</b>.

### -param _L

The length in bytes of the transfer. This value also was passed to 
     <b>NdisMSetupDmaTransfer</b>.

### -param _M_

<b>TRUE</b> if the transfer was from the host to the NIC, as, for example, a send operation.

## -remarks

<b>NdisMCompleteDmaTransfer</b> must be called with 
    <i>WriteToDevice</i> set to <b>TRUE</b> before the transferred data is considered present in the NIC's memory. 
    <b>NdisMCompleteDmaTransfer</b> must be called with 
    <i>WriteToDevice</i> set to <b>FALSE</b> before the transferred data can be read from host memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetupdmatransfer">NdisMSetupDmaTransfer</a>