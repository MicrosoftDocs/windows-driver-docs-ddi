---
UID: NC:dot11wdi.MINIPORT_WDI_IDLE_NOTIFICATION
title: MINIPORT_WDI_IDLE_NOTIFICATION
author: windows-driver-content
description: NDIS calls the MiniportWdiIdleNotification handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.
old-location: netvista\miniportwdiidlenotification.htm
old-project: netvista
ms.assetid: BA050C7C-A593-469E-9212-B363F2D2A409
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdiidlenotification, MiniportWdiIdleNotification callback function [Network Drivers Starting with Windows Vista], MiniportWdiIdleNotification, MINIPORT_WDI_IDLE_NOTIFICATION, MINIPORT_WDI_IDLE_NOTIFICATION, dot11wdi/MiniportWdiIdleNotification
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
-	MiniportWdiIdleNotification
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_IDLE_NOTIFICATION callback


## -description


NDIS calls the MiniportWdiIdleNotification handler   function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_IDLE_NOTIFICATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_IDLE_NOTIFICATION MiniportWdiIdleNotification;

NDIS_STATUS MiniportWdiIdleNotification(
  _In_ NDIS_HANDLE MiniportAdapterContext,
  _In_ BOOLEAN     ForceIdle
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param ForceIdle [in]

A BOOLEAN value that, when set to TRUE, specifies that the miniport driver must not veto the idle notification and must continue with the low-power state transition.

For more information about the ForceIdle parameter, see the Remarks section.



## -returns



            MiniportWdiIdleNotification can return any of the following return values.
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
The miniport driver successfully handled the idle notification. The notification is left in a pending state until the miniport driver calls <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_idle_notification_complete.md">NdisWdiIdleNotificationComplete</a>.

<div class="alert"><b>Note</b>  The miniport driver must not return NDIS_STATUS_SUCCESS from <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_idle_notification.md">MiniportWdiIdleNotification</a>.
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

<div class="alert"><b>Note</b>  <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_idle_notification.md">MiniportWdiIdleNotification</a> must not return this status code if the <i>ForceIdle</i> parameter is set to <b>TRUE</b>.</div>
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



## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_idle_notification_complete.md">NdisWdiIdleNotificationComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_IDLE_NOTIFICATION callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

