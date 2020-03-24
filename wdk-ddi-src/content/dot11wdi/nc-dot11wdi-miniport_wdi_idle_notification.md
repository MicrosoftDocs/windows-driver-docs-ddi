---
UID: NC:dot11wdi.MINIPORT_WDI_IDLE_NOTIFICATION
title: MINIPORT_WDI_IDLE_NOTIFICATION (dot11wdi.h)
description: NDIS calls the MiniportWdiIdleNotification handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.
old-location: netvista\miniportwdiidlenotification.htm
tech.root: netvista
ms.assetid: BA050C7C-A593-469E-9212-B363F2D2A409
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_IDLE_NOTIFICATION callback function"]
ms.keywords: MINIPORT_WDI_IDLE_NOTIFICATION, MINIPORT_WDI_IDLE_NOTIFICATION callback, MiniportWdiIdleNotification, MiniportWdiIdleNotification callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiIdleNotification, netvista.miniportwdiidlenotification
f1_keywords:
 - "dot11wdi/MiniportWdiIdleNotification"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dot11wdi.h
api_name:
- MiniportWdiIdleNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_IDLE_NOTIFICATION callback function


## -description


NDIS calls the MiniportWdiIdleNotification handler   function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_IDLE_NOTIFICATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

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
The miniport driver successfully handled the idle notification. The notification is left in a pending state until the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_idle_notification_complete">NdisWdiIdleNotificationComplete</a>.

<div class="alert"><b>Note</b>  The miniport driver must not return NDIS_STATUS_SUCCESS from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a>.
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

<div class="alert"><b>Note</b>  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a> must not return this status code if the <i>ForceIdle</i> parameter is set to <b>TRUE</b>.</div>
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_idle_notification_complete">NdisWdiIdleNotificationComplete</a>
 

 

