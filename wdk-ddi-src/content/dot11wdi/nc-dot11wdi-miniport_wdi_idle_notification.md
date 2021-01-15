---
UID: NC:dot11wdi.MINIPORT_WDI_IDLE_NOTIFICATION
title: MINIPORT_WDI_IDLE_NOTIFICATION (dot11wdi.h)
description: NDIS calls the MiniportWdiIdleNotification handler function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.
old-location: netvista\miniportwdiidlenotification.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_IDLE_NOTIFICATION callback function"]
ms.keywords: MINIPORT_WDI_IDLE_NOTIFICATION, MINIPORT_WDI_IDLE_NOTIFICATION callback, MiniportWdiIdleNotification, MiniportWdiIdleNotification callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiIdleNotification, netvista.miniportwdiidlenotification
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
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_WDI_IDLE_NOTIFICATION
 - dot11wdi/MINIPORT_WDI_IDLE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MINIPORT_WDI_IDLE_NOTIFICATION
---

# MINIPORT_WDI_IDLE_NOTIFICATION callback function


## -description

NDIS calls the MiniportWdiIdleNotification handler   function to start the NDIS selective suspend operation on an idle network adapter. Through this operation, the network adapter is suspended and transitioned to a low-power state.

This is a WDI miniport handler inside [NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS](ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md).

> [!Note]
> You must declare the function by using the **MINIPORT_WDI_IDLE_NOTIFICATION** type. For more
   information, see the following Examples section.

## -parameters

### -param MiniportAdapterContext 

[in]
The handle to the context area that the miniport driver allocated.

### -param ForceIdle 

[in]
A BOOLEAN value that, when set to TRUE, specifies that the miniport driver must not veto the idle notification and must continue with the low-power state transition.

For more information about the ForceIdle parameter, see the Remarks section.

## -returns

MiniportWdiIdleNotification can return any of the following return values.

|Return code|Description|
|--- |--- |
|**NDIS_STATUS_PENDING**|The miniport driver successfully handled the idle notification. The notification is left in a pending state until the miniport driver calls [NdisWdiIdleNotificationComplete](nc-dot11wdi-ndis_wdi_idle_notification_complete.md). **Note:** The miniport driver must not return NDIS_STATUS_SUCCESS from [MiniportWdiIdleNotification](nc-dot11wdi-miniport_wdi_idle_notification.md).|
|**NDIS_STATUS_BUSY**|The miniport driver vetoed the idle notification because the network adapter is still being used. **Note:** [MiniportWdiIdleNotification](nc-dot11wdi-miniport_wdi_idle_notification.md) must not return this status code if the _ForceIdle_ parameter is set to **TRUE**.|
|**NDIS_STATUS_FAILURE**|The miniport driver could not issue a bus-specific IRP successfully.|

## -see-also

[NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS](ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md)


[NdisWdiIdleNotificationComplete](nc-dot11wdi-ndis_wdi_idle_notification_complete.md)

