---
UID: NC:ndis.MINIPORT_IDLE_NOTIFICATION
title: MINIPORT_IDLE_NOTIFICATION (ndis.h)
description: NDIS calls the MiniportIdleNotification handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.
old-location: netvista\miniportidlenotification.htm
tech.root: netvista
ms.assetid: D679DEF0-1229-4731-8024-4DEDAE5B0185
ms.date: 05/02/2018
ms.keywords: MINIPORT_IDLE_NOTIFICATION, MINIPORT_IDLE_NOTIFICATION callback, MiniportIdleNotification, MiniportIdleNotification callback function [Network Drivers Starting with Windows Vista], ndis/MiniportIdleNotification, netvista.miniportidlenotification
ms.topic: callback
f1_keywords:
 - "ndis/MiniportIdleNotification"
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
- MiniportIdleNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_IDLE_NOTIFICATION callback function


## -description



NDIS calls the  <i>MiniportIdleNotification</i> handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.




## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for a network adapter.


### -param ForceIdle [in]

A <b>BOOLEAN</b> value that, when set to <b>TRUE</b>, specifies that the miniport driver must not veto the idle notification and must continue with the low-power state transition.

For more information about the <i>ForceIdle</i> parameter, see the Remarks section.


## -returns



<i>MiniportIdleNotification</i> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver successfully handled the idle notification. The notification is left in a pending state until the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a>.

<div class="alert"><b>Note</b>  The miniport driver must not return NDIS_STATUS_SUCCESS from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a>.
</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUSY</b></dt>
</dl>
</td>
<td width="60%">

       The miniport driver vetoed the idle notification because the network adapter is still being used.

<div class="alert"><b>Note</b>  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> must not return this status code if the <i>ForceIdle</i> parameter is set to <b>TRUE</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver could not issue a bus-specific IRP successfully.

</td>
</tr>
</table>
 




## -remarks



The <i>MiniportIdleNotification</i> handler function is required for miniport drivers that support the NDIS selective suspend interface. For more information about how the driver registers its selective suspend handler functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-ndis-selective-suspend-handler-functions">Registering NDIS Selective Suspend Handler Functions</a>.

NDIS sets the <i>ForceIdle</i> parameter to <b>FALSE</b> when the network adapter has been inactive for longer than the idle time-out period. Therefore, NDIS <i>selectively suspends</i> only the network adapter.



The duration of the idle time-out period is specified by the value of the <b>*SSIdleTimeout</b> INF keyword. For more information about this keyword, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/standardized-inf-keywords-for-ndis-selective-suspend">Standardized INF Keywords for NDIS Selective Suspend</a>. 



<div class="alert"><b>Note</b>  NDIS sets the <i>ForceIdle</i> parameter to <b>TRUE</b> only when a system that is compliant with the Always On Always Connected (AOAC) technology is transitioning to a Connected Standby state. </div>
<div> </div>
If the miniport driver determines that the network adapter is being used, it can veto the idle notification request by returning NDIS_STATUS_BUSY. This causes NDIS to restart the monitor of activity on the network adapter. 

If the adapter becomes inactive again within the idle time-out period, NDIS calls <i>MiniportIdleNotification</i>. 

<div class="alert"><b>Note</b>  The miniport driver must not return NDIS_STATUS_BUSY  if the <i>ForceIdle</i> parameter is set to <b>TRUE</b>.</div>
<div> </div>
After the idle notification is issued, it can be canceled and completed in the following way:

<ul>
<li>
NDIS can cancel the outstanding idle notification if the following conditions are true:

<ul>
<li>
An overlying protocol or filter driver issues either a send packet request or an OID request to the miniport driver. 


</li>
<li>
The underlying adapter signals a wake-up event, such as receiving a packet that matches a wake-on-LAN (WOL) pattern or detecting a change in its media connection status. 


</li>
</ul>
NDIS cancels the idle notification by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a>. When this handler function is called, the miniport driver cancels any bus-specific IRPs that it may have previously issued for the idle notification. 
Finally, the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a> to complete the idle notification.

</li>
<li>
 After the network adapter is in a low-power state, the miniport driver can complete the idle notification itself in order to resume the adapter to a full-power state. The reasons for doing this are specific to the design and requirements of the driver and adapter. 

The miniport driver completes the idle notification  by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a>. For more information about how the miniport driver completes the idle notification, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/completing-the-ndis-selective-suspend-idle-notification">Completing the NDIS Selective Suspend Idle Notification</a>.

</li>
</ul>
For more information on how to handle idle notifications for NDIS selective suspend, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-the-ndis-selective-suspend-idle-notification">Handling the NDIS Selective Suspend Idle Notification</a>.

For guidelines on how to implement the <i>MiniportIdleNotification</i> handler function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/implementing-a-miniportidlenotification-handler-function">Implementing a MiniportIdleNotification Handler Function</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a>
 

 

