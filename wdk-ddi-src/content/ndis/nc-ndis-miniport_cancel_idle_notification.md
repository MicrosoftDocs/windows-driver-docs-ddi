---
UID: NC:ndis.MINIPORT_CANCEL_IDLE_NOTIFICATION
title: MINIPORT_CANCEL_IDLE_NOTIFICATION
author: windows-driver-content
description: NDIS calls the MiniportCancelIdleNotification handler function to notify the miniport driver that NDIS has detected activity on the suspended network adapter.
old-location: netvista\miniportcancelidlenotification.htm
old-project: netvista
ms.assetid: 9965E4EA-10E3-4240-9E4F-D3B49B8F9593
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_CANCEL_IDLE_NOTIFICATION, MiniportCancelIdleNotification, MiniportCancelIdleNotification callback function [Network Drivers Starting with Windows Vista], ndis/MiniportCancelIdleNotification, netvista.miniportcancelidlenotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportCancelIdleNotification
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_CANCEL_IDLE_NOTIFICATION callback


## -description



NDIS calls the <i>MiniportCancelIdleNotification</i> handler function to notify the miniport driver that NDIS has detected activity on the suspended network adapter. Because of this, NDIS cancels the idle notification so that the network adapter can be transitioned to a full-power state.




## -prototype


````
MINIPORT_CANCEL_IDLE_NOTIFICATION MiniportCancelIdleNotification;

VOID MiniportCancelIdleNotification(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for a network adapter.


## -returns



None




## -remarks



The <i>MiniportCancelIdleNotification</i> handler function is required for miniport drivers that support the NDIS selective suspend interface. For more information about how the driver registers its selective suspend handler functions, see <a href="https://msdn.microsoft.com/D4125F14-8356-4D9E-A287-D35D3BF69182">Registering NDIS Selective Suspend Handler Functions</a>.

NDIS calls the miniport driver's <a href="..\ndis\nc-ndis-miniport_idle_notification.md">MiniportIdleNotification</a> handler function to start an NDIS selective suspend operation on an idle network adapter. After the network adapter has been suspended and transitioned to a low-power state, NDIS can cancel the outstanding idle notification if any of the following conditions are true:

<ul>
<li>
An overlying protocol or filter driver issues either a send packet request or an OID request to the miniport driver. 


</li>
<li>
The underlying adapter signals a wake-up event, such as receiving a packet that matches a wake-on-LAN (WOL) pattern or detecting a change in its media connection status. 


</li>
</ul>
NDIS cancels the idle notification by calling <i>MiniportCancelIdleNotification</i>. When this handler function is called, the miniport driver first cancels any bus-specific I/O request packets (IRPs) that it may have previously issued for the idle notification. 
Finally, the miniport driver calls <a href="..\ndis\nf-ndis-ndismidlenotificationcomplete.md">NdisMIdleNotificationComplete</a> to complete the idle notification.

For more information about how NDIS cancels the idle notification, see <a href="https://msdn.microsoft.com/14C19F15-9D0E-4F37-942C-7F7AFE1EBA0B">Canceling the NDIS Selective Suspend Idle Notification</a>.

For guidelines on how to implement the <i>MiniportCancelIdleNotification</i> handler function and IRP completion routines, see <a href="https://msdn.microsoft.com/51C25573-5723-44F9-B498-EBEF6756F3B0">Implementing a MiniportCancelIdleNotification Handler Function</a>.




## -see-also

<a href="..\ndis\nf-ndis-ndismidlenotificationcomplete.md">NdisMIdleNotificationComplete</a>



<a href="..\ndis\nc-ndis-miniport_idle_notification.md">MiniportIdleNotification</a>



<a href="..\wdm\nf-wdm-iocancelirp.md">IoCancelIrp</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CANCEL_IDLE_NOTIFICATION callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

