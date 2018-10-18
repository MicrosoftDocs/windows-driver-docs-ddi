---
UID: NC:dot11wdi.NDIS_WDI_RX_INORDER_DATA_IND
title: NDIS_WDI_RX_INORDER_DATA_IND
author: windows-driver-content
description: The NdisWdiRxInorderDataIndication callback function informs the RxMgr that a list of specified RX frames in the correct order are present.
old-location: netvista\ndiswdirxinorderdataindication.htm
tech.root: netvista
ms.assetid: F2F92DAE-6C13-4EE6-9DE7-B77F5FAFAE60
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_RX_INORDER_DATA_IND, NDIS_WDI_RX_INORDER_DATA_IND callback, NdisWdiRxInorderDataIndication, NdisWdiRxInorderDataIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxInorderDataIndication, netvista.ndiswdirxinorderdataindication
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	NdisWdiRxInorderDataIndication
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_RX_INORDER_DATA_IND callback function


## -description


The 
  NdisWdiRxInorderDataIndication callback function informs the RxMgr that a list of specified RX frames in the correct order are present.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param IndicationLevel [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn926110">WDI_RX_INDICATION_LEVEL</a> enumeration value that specifies the RX indication level.


### -param PeerId [in]

The peer ID.


### -param ExTid [in]

The extended TID.


### -param pRxThrottleParams [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567241">NDIS_RECEIVE_THROTTLE_PARAMETERS</a> structure.


### -param *pWifiStatus [out]

Status from WDI for the <i>NdisWdiRxInorderDataIndication</i>.  See the <i>Remarks</i> section for more information.


## -returns



This callback function does not return a value.




## -remarks



The RxEngine uses WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC if this indication is the first data indication <b>NdisWdiRxInorderDataIndication</b>) of a DPC.  Subsequent data indications use WDI_RX_INDICATION_DISPATCH_GENERAL.  If indications are made at passive level, then the RxEngine must use WDI_RX_INDICATION_PASSIVE.  Indications made in the context of <a href="https://msdn.microsoft.com/483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A">MiniportWdiRxResume</a> must use WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES.  This parameter gives the RxMgr information necessary for limiting the lifetime of DPCs.

WDI_RX_INDICATION_FLAG_RESOURCES can be bitwise ORed with the other enum values to cause RxMgr to set NDIS_RECEIVE_FLAG_RESOURCES flags on the data indication.

The RxMgr issues  <a href="https://msdn.microsoft.com/195F4143-4889-4788-BAF5-2F1ED6E4E50A">MiniportWdiRxGetMpdus</a> requests to pull the received data.

If the target is not capable of RX frame classification and uses separate indications for  RX frames from different PeerID/TID pairs, the PeerID is set to a wildcard (0xFFFF) and TID is  set to WDI_EXT_TID_UNKNOWN.

In the case where the target/TAL takes full responsibility for reordering buffer management, it also performs all discard actions. No MPDU status is required.

PNDIS_RECEIVE_THROTTLE_PARAMETERS points to the <i>ReceiveThrottleParameters</i>, which is passed by NDIS for interrupts registered with NDIS.  This only needs to be set for WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC.  All other data indications should pass NULL, as this parameter is ignored.

If the RxMgr sets the WDI_STATUS to success, the RxEngine can create more data indications in the context of the same DPC.  If the RxMgr sets the WDI_STATUS to pause, the RxEngine must not create data indications until the RxMgr issues a <a href="https://msdn.microsoft.com/483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A">MiniportWdiRxResume</a> and should exit dispatch level as soon as possible.

The RxEngine can choose how to handle incoming data while paused.  If possible, it should just buffer the data.  Dropping data is also acceptable.

The RxMgr tracks the number of frames indicated to NDIS against the limit specified in PNDIS_RECEIVE_THROTTLE_PARAMETERS. The RxMgr also tracks the time spent at dispatch.  When limits are reached, the RxMgr returns NDIS_STATUS_PAUSED.  The RxEngine should return/exit DPC as soon as possible, and must not indicate any more <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures (via <b>NdisWdiRxInorderDataIndication</b>) until RxMgr calls <a href="https://msdn.microsoft.com/483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A">MiniportWdiRxResume</a>.  Any <b>NET_BUFFER_LIST</b> structures that are given to RxMgr (via <a href="https://msdn.microsoft.com/195F4143-4889-4788-BAF5-2F1ED6E4E50A">MiniportWdiRxGetMpdus</a>) and have not been indicated up yet are indicated up to NDIS in a different context to avoid spending too much time at DPC.  Once that backlog has been cleared, RxMgr unpauses the RxEngine by invoking  <i>MiniportWdiRxResume</i>.




## -see-also




<a href="https://msdn.microsoft.com/195F4143-4889-4788-BAF5-2F1ED6E4E50A">MiniportWdiRxGetMpdus</a>



<a href="https://msdn.microsoft.com/483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A">MiniportWdiRxResume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567241">NDIS_RECEIVE_THROTTLE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn926110">WDI_RX_INDICATION_LEVEL</a>
 

 

