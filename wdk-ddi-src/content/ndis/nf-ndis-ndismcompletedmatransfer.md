---
UID: NF:ndis.NdisMCompleteDmaTransfer
title: NdisMCompleteDmaTransfer macro
author: windows-driver-content
description: The NdisMCompleteDmaTransfer function indicates that a system DMA transfer operation has completed. It resets the system DMA controller in preparation for further DMA transfers.
old-location: netvista\ndismcompletedmatransfer.htm
old-project: netvista
ms.assetid: 12a8062a-6d4b-4757-a076-56aeb5e4e48c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisMCompleteDmaTransfer, NdisMCompleteDmaTransfer, netvista.ndismcompletedmatransfer, NdisMCompleteDmaTransfer macro [Network Drivers Starting with Windows Vista], dma_ref_bd601fef-cf06-42ff-9906-d3bf8edef72f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: ndis.h
req.dll: 
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndis.h
apiname: 
-	NdisMCompleteDmaTransfer
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisMCompleteDmaTransfer macro


## -description


The 
  <b>NdisMCompleteDmaTransfer</b> function indicates that a system DMA transfer operation has completed. It
  resets the system DMA controller in preparation for further DMA transfers.


## -syntax


````
VOID NdisMCompleteDmaTransfer(
  [out] PNDIS_STATUS Status,
  [in]  NDIS_HANDLE  MiniportDmaHandle,
  [in]  PNDIS_BUFFER Buffer,
  [in]  ULONG        Offset,
  [in]  ULONG        Length,
  [in]  BOOLEAN      WriteToDevice
);
````


## -parameters




### -param _S

TBD


### -param _H

TBD


### -param _B

TBD


### -param _O

TBD


### -param _L

TBD


### -param _M_

TBD




#### - Length [in]

The length in bytes of the transfer. This value also was passed to 
     <b>NdisMSetupDmaTransfer</b>.


#### - MiniportDmaHandle [in]

The handle returned when the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
     called the 
     <mshelp:link keywords="netvista.ndismregisterdmachannel" tabindex="0"><b>
     NdisMRegisterDmaChannel</b></mshelp:link> function.


#### - WriteToDevice [in]

<b>TRUE</b> if the transfer was from the host to the NIC, as, for example, a send operation.


#### - Status [out]

A pointer to a caller-supplied variable in which this function returns the final status of the DMA
     transfer, which can be one of the following:
     




#### - Offset [in]

The byte offset at which the transfer began. This value also was passed to 
     <b>NdisMSetupDmaTransfer</b>.


#### - Buffer [in]

A pointer to the buffer descriptor previously passed to 
     <a href="..\ndis\nf-ndis-ndismsetupdmatransfer.md">NdisMSetupDmaTransfer</a>.


##### - Status.NDIS_STATUS_SUCCESS

The data has been transferred and flushed to host memory or to the device to maintain data
       integrity.


##### - Status.NDIS_STATUS_RESOURCES

The DMA controller was released but the data transfer might be incoherent.


## -remarks


<b>NdisMCompleteDmaTransfer</b> must be called with 
    <i>WriteToDevice</i> set to <b>TRUE</b> before the transferred data is considered present in the NIC's memory. 
    <b>NdisMCompleteDmaTransfer</b> must be called with 
    <i>WriteToDevice</i> set to <b>FALSE</b> before the transferred data can be read from host memory.



## -see-also

<a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndismsetupdmatransfer.md">NdisMSetupDmaTransfer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCompleteDmaTransfer macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

