---
UID: NC:ndis.MINIPORT_CANCEL_IDLE_NOTIFICATION
title: MINIPORT_CANCEL_IDLE_NOTIFICATION (ndis.h)
description: NDIS calls the MiniportCancelIdleNotification handler function to notify the miniport driver that NDIS has detected activity on the suspended network adapter.
old-location: netvista\miniportcancelidlenotification.htm
tech.root: netvista
ms.assetid: 9965E4EA-10E3-4240-9E4F-D3B49B8F9593
ms.date: 05/02/2018
keywords: ["MINIPORT_CANCEL_IDLE_NOTIFICATION callback function"]
ms.keywords: MINIPORT_CANCEL_IDLE_NOTIFICATION, MINIPORT_CANCEL_IDLE_NOTIFICATION callback, MiniportCancelIdleNotification, MiniportCancelIdleNotification callback function [Network Drivers Starting with Windows Vista], ndis/MiniportCancelIdleNotification, netvista.miniportcancelidlenotification
f1_keywords:
 - "ndis/MiniportCancelIdleNotification"
 - "MiniportCancelIdleNotification"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- MiniportCancelIdleNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CANCEL_IDLE_NOTIFICATION callback function


## -description



NDIS calls the <i>MiniportCancelIdleNotification</i> handler function to notify the miniport driver that NDIS has detected activity on the suspended network adapter. Because of this, NDIS cancels the idle notification so that the network adapter can be transitioned to a full-power state.




## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for a network adapter.


## -remarks



The <i>MiniportCancelIdleNotification</i> handler function is required for miniport drivers that support the NDIS selective suspend interface. For more information about how the driver registers its selective suspend handler functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-ndis-selective-suspend-handler-functions">Registering NDIS Selective Suspend Handler Functions</a>.

NDIS calls the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> handler function to start an NDIS selective suspend operation on an idle network adapter. After the network adapter has been suspended and transitioned to a low-power state, NDIS can cancel the outstanding idle notification if any of the following conditions are true:

<ul>
<li>
An overlying protocol or filter driver issues either a send packet request or an OID request to the miniport driver. 


</li>
<li>
The underlying adapter signals a wake-up event, such as receiving a packet that matches a wake-on-LAN (WOL) pattern or detecting a change in its media connection status. 


</li>
</ul>
NDIS cancels the idle notification by calling <i>MiniportCancelIdleNotification</i>. When this handler function is called, the miniport driver first cancels any bus-specific I/O request packets (IRPs) that it may have previously issued for the idle notification. 
Finally, the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a> to complete the idle notification.

For more information about how NDIS cancels the idle notification, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/canceling-the-ndis-selective-suspend-idle-notification">Canceling the NDIS Selective Suspend Idle Notification</a>.

For guidelines on how to implement the <i>MiniportCancelIdleNotification</i> handler function and IRP completion routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/implementing-a-miniportcancelidlenotification-handler-function">Implementing a MiniportCancelIdleNotification Handler Function</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocancelirp">IoCancelIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a>
 

 

