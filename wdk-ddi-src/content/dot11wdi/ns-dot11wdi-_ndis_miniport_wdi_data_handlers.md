---
UID: NS:dot11wdi._NDIS_MINIPORT_WDI_DATA_HANDLERS
title: "_NDIS_MINIPORT_WDI_DATA_HANDLERS"
author: windows-driver-content
description: The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.
old-location: netvista\ndis_miniport_wdi_data_handlers.htm
old-project: netvista
ms.assetid: DBDB5F08-9988-4D9B-A731-DA65BBA67813
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_WDI_DATA_HANDLERS, PNDIS_MINIPORT_WDI_DATA_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_WDI_DATA_HANDLERS, dot11wdi/NDIS_MINIPORT_WDI_DATA_HANDLERS, dot11wdi/PNDIS_MINIPORT_WDI_DATA_HANDLERS, netvista.ndis_miniport_wdi_data_handlers"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: Ndis.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	NDIS_MINIPORT_WDI_DATA_HANDLERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_WDI_DATA_HANDLERS, *PNDIS_MINIPORT_WDI_DATA_HANDLERS
---

# _NDIS_MINIPORT_WDI_DATA_HANDLERS structure


## -description


The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_WDI_DATA_HANDLERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS.
     

To indicate the version of the NDIS_MINIPORT_WDI_DATA_HANDLERS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_DATA_HANDLERS_REVISION_1.


### -field TxAbortHandler

The entry point of the <a href="https://msdn.microsoft.com/FA6BEAE9-5D48-463E-A398-518737D78867">MiniportWdiTxAbort</a> handler function.


### -field TxTargetDescInitHandler

The entry point of the <a href="https://msdn.microsoft.com/EAFE6F7D-6820-4626-863D-C28FBFFCE6A0">MiniportWdiTxTargetDescInit</a> handler function.


### -field TxTargetDescDeInitHandler

The entry point of the <a href="https://msdn.microsoft.com/C7C6C175-5E9D-4C6B-8A6B-F903DDE4DC78">MiniportWdiTxTargetDescDeInit</a> handler function.


### -field TxDataSendHandler

The entry point of the <a href="https://msdn.microsoft.com/A9EB1E8C-BD10-450F-9F4B-CD19C8AF13EA">MiniportWdiTxDataSend</a> handler function.


### -field TxTalSendHandler

The entry point of the <a href="https://msdn.microsoft.com/42489ADA-78BF-4EBF-A6EC-5484F82C46ED">MiniportWdiTxTalSend</a> handler function.


### -field TxTalSendCompleteHandler

The entry point of the <a href="https://msdn.microsoft.com/347B069F-76B6-42D5-9613-7D0214C2FEDB">MiniportWdiTxTalSendComplete</a> handler function.


### -field TxTalQueueInOrderHandler

The entry point of the <a href="https://msdn.microsoft.com/E82E19EA-4336-49DE-9CE4-DFBA0A347DFE">MiniportWdiTxTalQueueInOrder</a> handler function.


### -field TxPeerBacklogHandler

The entry point of the <a href="https://msdn.microsoft.com/49DC9034-9A50-4B0F-B7F7-A06147D1046F">MiniportWdiTxPeerBacklog</a> handler function.


### -field RxStopHandler

The entry point of the <a href="https://msdn.microsoft.com/AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD">MiniportWdiRxStop</a> handler function.


### -field RxFlushHandler

The entry point of the <a href="https://msdn.microsoft.com/76945A84-A6DB-4753-B04E-32249359B8C6">MiniportWdiRxFlush</a> handler function.


### -field RxRestartHandler

The entry point of the <a href="https://msdn.microsoft.com/465716C7-A157-4B06-BAE2-F18A08126040">MiniportWdiRxRestart</a> handler function.


### -field RxGetMpdusHandler

The entry point of the <a href="https://msdn.microsoft.com/195F4143-4889-4788-BAF5-2F1ED6E4E50A">MiniportWdiRxGetMpdus</a> handler function.


### -field RxReturnFramesHandler

The entry point of the <a href="https://msdn.microsoft.com/BF2DB7C6-97F9-454B-8DED-E8CC21A4F07F">MiniportWdiRxReturnFrames</a> handler function.


### -field RxResumeHandler

The entry point of the <a href="https://msdn.microsoft.com/483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A">MiniportWdiRxResume</a> handler function.


### -field RxThrottleHandler

The entry point of the <a href="https://msdn.microsoft.com/A5985C6D-3768-4ACE-B52B-3D3494334114">MiniportWdiRxThrottle</a> handler function.


### -field RxPpduRssiHandler

The entry point of the <a href="https://msdn.microsoft.com/34C34C42-E5E1-44F6-AC81-ADC77206DED0">MiniportWdiRxPpduRssi</a> handler function.


### -field TalTxRxStartHandler

The entry point of the <a href="https://msdn.microsoft.com/6F88F4B1-8D2A-41CC-8D60-C1CF91ED072A">MiniportWdiTalTxRxStart</a> handler function.


### -field TalTxRxStopHandler

The entry point of the <a href="https://msdn.microsoft.com/21841DC6-B95F-4372-BBD1-EA195832A118">MiniportWdiTalTxRxStop</a> handler function.


### -field TalTxRxAddPortHandler

The entry point of the <a href="https://msdn.microsoft.com/D3006A0B-B0E0-4FEA-864A-FA4B75594FB0">MiniportWdiTalTxRxAddPort</a> handler function.


### -field TalTxRxDeletePortHandler

The entry point of the <a href="https://msdn.microsoft.com/3DB6AC6F-2A6F-43E1-B98D-B4E5C8A87845">MiniportWdiTalTxRxDeletePort</a> handler function.


### -field TalTxRxSetPortOpModeHandler

The entry point of the <a href="https://msdn.microsoft.com/86F3005E-8BB3-4309-AFDE-7FA6E0427BFD">MiniportWdiTalTxRxSetPortOpMode</a> handler function.


### -field TalTxRxResetPortHandler

The entry point of the <a href="https://msdn.microsoft.com/BB584FC9-8048-42F4-AFA9-7BF6790EDD69">MiniportWdiTalTxRxResetPort</a> handler function.


### -field TalTxRxPeerConfigHandler

The entry point of the <a href="https://msdn.microsoft.com/48BB554D-A19E-46C0-8278-690A686A731D">MiniportWdiTalTxRxPeerConfig</a> handler function.


### -field TalTxRxPeerDeleteConfirmHandler

The entry point of the <a href="https://msdn.microsoft.com/993C600F-E2FA-46D7-AE66-77048B481660">MiniportWdiTalTxRxPeerDeleteConfirm</a> handler function.


### -field TxSuspectFrameAbortHandler

The entry point of the [MiniportWdiTxSuspectFrameAbort](nc-dot11wdi-miniport_wdi_tx_suspect_frame_list_abort.md) handler function.