---
UID: NC:dot11wdi.NDIS_WDI_RX_INORDER_DATA_IND
title: NDIS_WDI_RX_INORDER_DATA_IND
author: windows-driver-content
description: The NdisWdiRxInorderDataIndication callback function informs the RxMgr that a list of specified RX frames in the correct order are present.
old-location: netvista\ndiswdirxinorderdataindication.htm
old-project: netvista
ms.assetid: F2F92DAE-6C13-4EE6-9DE7-B77F5FAFAE60
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiswdirxinorderdataindication, NdisWdiRxInorderDataIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiRxInorderDataIndication, NDIS_WDI_RX_INORDER_DATA_IND, NDIS_WDI_RX_INORDER_DATA_IND, dot11wdi/NdisWdiRxInorderDataIndication
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
-	NdisWdiRxInorderDataIndication
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---

# NDIS_WDI_RX_INORDER_DATA_IND callback


## -description


The 
  NdisWdiRxInorderDataIndication callback function informs the RxMgr that a list of specified RX frames in the correct order are present.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_RX_INORDER_DATA_IND NdisWdiRxInorderDataIndication;

VOID NdisWdiRxInorderDataIndication(
  _In_  NDIS_HANDLE                       NdisMiniportDataPathHandle,
  _In_  WDI_RX_INDICATION_LEVEL           IndicationLevel,
  _In_  WDI_PEER_ID                       PeerId,
  _In_  WDI_EXTENDED_TID                  ExTid,
  _In_  PNDIS_RECEIVE_THROTTLE_PARAMETERS pRxThrottleParams,
  _Out_ NDIS_STATUS                       *pWifiStatus
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param IndicationLevel [in]

A <a href="..\dot11wdi\ne-dot11wdi-_wdi_rx_indication_level.md">WDI_RX_INDICATION_LEVEL</a> enumeration value that specifies the RX indication level.


### -param PeerId [in]

The peer ID.


### -param ExTid [in]

The extended TID.


### -param pRxThrottleParams [in]

Pointer to a <a href="..\ndis\ns-ndis-_ndis_receive_throttle_parameters.md">NDIS_RECEIVE_THROTTLE_PARAMETERS</a> structure.


### -param *pWifiStatus [out]

Status from WDI for the <i>NdisWdiRxInorderDataIndication</i>.  See the <i>Remarks</i> section for more information.


## -returns



This callback function does not return a value.




## -remarks



The RxEngine uses WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC if this indication is the first data indication <b>NdisWdiRxInorderDataIndication</b>) of a DPC.  Subsequent data indications use WDI_RX_INDICATION_DISPATCH_GENERAL.  If indications are made at passive level, then the RxEngine must use WDI_RX_INDICATION_PASSIVE.  Indications made in the context of <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a> must use WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES.  This parameter gives the RxMgr information necessary for limiting the lifetime of DPCs.

WDI_RX_INDICATION_FLAG_RESOURCES can be bitwise ORed with the other enum values to cause RxMgr to set NDIS_RECEIVE_FLAG_RESOURCES flags on the data indication.

The RxMgr issues  <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_get_mpdus.md">MiniportWdiRxGetMpdus</a> requests to pull the received data.

If the target is not capable of RX frame classification and uses separate indications for  RX frames from different PeerID/TID pairs, the PeerID is set to a wildcard (0xFFFF) and TID is  set to WDI_EXT_TID_UNKNOWN.

In the case where the target/TAL takes full responsibility for reordering buffer management, it also performs all discard actions. No MPDU status is required.

PNDIS_RECEIVE_THROTTLE_PARAMETERS points to the <i>ReceiveThrottleParameters</i>, which is passed by NDIS for interrupts registered with NDIS.  This only needs to be set for WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC.  All other data indications should pass NULL, as this parameter is ignored.

If the RxMgr sets the WDI_STATUS to success, the RxEngine can create more data indications in the context of the same DPC.  If the RxMgr sets the WDI_STATUS to pause, the RxEngine must not create data indications until the RxMgr issues a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a> and should exit dispatch level as soon as possible.

The RxEngine can choose how to handle incoming data while paused.  If possible, it should just buffer the data.  Dropping data is also acceptable.

The RxMgr tracks the number of frames indicated to NDIS against the limit specified in PNDIS_RECEIVE_THROTTLE_PARAMETERS. The RxMgr also tracks the time spent at dispatch.  When limits are reached, the RxMgr returns NDIS_STATUS_PAUSED.  The RxEngine should return/exit DPC as soon as possible, and must not indicate any more <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures (via <b>NdisWdiRxInorderDataIndication</b>) until RxMgr calls <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a>.  Any <b>NET_BUFFER_LIST</b> structures that are given to RxMgr (via <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_get_mpdus.md">MiniportWdiRxGetMpdus</a>) and have not been indicated up yet are indicated up to NDIS in a different context to avoid spending too much time at DPC.  Once that backlog has been cleared, RxMgr unpauses the RxEngine by invoking  <i>MiniportWdiRxResume</i>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_rx_indication_level.md">WDI_RX_INDICATION_LEVEL</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_get_mpdus.md">MiniportWdiRxGetMpdus</a>



<a href="..\ndis\ns-ndis-_ndis_receive_throttle_parameters.md">NDIS_RECEIVE_THROTTLE_PARAMETERS</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_RX_INORDER_DATA_IND callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

