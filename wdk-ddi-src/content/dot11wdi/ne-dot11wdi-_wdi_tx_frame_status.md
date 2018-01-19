---
UID: NE:dot11wdi._WDI_TX_FRAME_STATUS
title: _WDI_TX_FRAME_STATUS
author: windows-driver-content
description: The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values.
old-location: netvista\wdi_tx_frame_status.htm
old-project: netvista
ms.assetid: 6ea8a7ac-96dc-4337-884f-d30fbee1f760
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_TX_FRAME_STATUS, WDI_TX_FRAME_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TX_FRAME_STATUS
req.alt-loc: dot11wdi.h
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
req.typenames: WDI_TX_FRAME_STATUS
---

# _WDI_TX_FRAME_STATUS enumeration



## -description
The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values.



## -syntax

````
typedef enum _WDI_TX_FRAME_STATUS { 
  WDI_TxFrameStatus_Ok                 = 0,
  WDI_TxFrameStatus_Discard            = 1,
  WDI_TxFrameStatus_NoAck              = 2,
  WDI_TxFrameStatus_TransferCancelled  = 3,
  WDI_TxFrameStatus_SendCancelled      = 4,
  WDI_TxFrameStatus_SendPostponed      = 5,
  WDI_TxFrameStatus_TransferFailed     = 128
} WDI_TX_FRAME_STATUS;
````


## -enum-fields

### -field WDI_TxFrameStatus_Ok

Frame transmitted without errors.


### -field WDI_TxFrameStatus_Discard

The frame was discarded to make room for higher priority frames.


### -field WDI_TxFrameStatus_NoAck

Transmission failed after exhausting the maximum number of retries.


### -field WDI_TxFrameStatus_TransferCancelled

TX stop requested.


### -field WDI_TxFrameStatus_SendCancelled

TX stop requested.


### -field WDI_TxFrameStatus_SendPostponed

The frame could not be transmitted at this time (for example, the peer is in PS). The frame should be transferred at a suitable time, when the corresponding TX queue is unpaused. This status is not allowed for targets that have <b>TargetPriorityQueueing</b> set to TRUE.


### -field WDI_TxFrameStatus_TransferFailed

The transfer failed.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_TX_FRAME_STATUS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

