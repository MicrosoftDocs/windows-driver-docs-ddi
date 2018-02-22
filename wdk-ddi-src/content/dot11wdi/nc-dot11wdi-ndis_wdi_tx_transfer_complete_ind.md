---
UID: NC:dot11wdi.NDIS_WDI_TX_TRANSFER_COMPLETE_IND
title: NDIS_WDI_TX_TRANSFER_COMPLETE_IND
author: windows-driver-content
description: The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target. Frames with different TX Status values are completed in separate indications.
old-location: netvista\ndiswditxtransfercompleteindication.htm
old-project: netvista
ms.assetid: BC66C993-F571-4EB9-8163-65B038ECE754
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndiswditxtransfercompleteindication, NdisWdiTxTransferCompleteIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiTxTransferCompleteIndication, NDIS_WDI_TX_TRANSFER_COMPLETE_IND, NDIS_WDI_TX_TRANSFER_COMPLETE_IND, dot11wdi/NdisWdiTxTransferCompleteIndication
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	NdisWdiTxTransferCompleteIndication
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---

# NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback


## -description


The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target.
Frames with different TX Status values are completed in separate indications.

If the TX status is a failure code, an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a> is not indicated for any of the frames in the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> (NBL) chain.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_TX_TRANSFER_COMPLETE_IND NdisWdiTxTransferCompleteIndication;

VOID NdisWdiTxTransferCompleteIndication(
  _In_ NDIS_HANDLE         NdisMiniportDataPathHandle,
  _In_ WDI_TX_FRAME_STATUS WifiTxFrameStatus,
  _In_ PNET_BUFFER_LIST    pNBL
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param WifiTxFrameStatus [in]

The TX status, specified as a <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a> value.


### -param pNBL [in]

The null-terminated list of frame buffers that have been transferred to the target.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

