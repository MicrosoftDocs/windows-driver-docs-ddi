---
UID: NC:dot11wdi.NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
title: NDIS_WDI_IDLE_NOTIFICATION_CONFIRM (dot11wdi.h)
description: Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.
old-location: netvista\ndiswdiidlenotificationconfirm.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback function"]
ms.keywords: NDIS_WDI_IDLE_NOTIFICATION_CONFIRM, NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback, NdisWdiIdleNotificationConfirm, NdisWdiIdleNotificationConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiIdleNotificationConfirm, netvista.ndiswdiidlenotificationconfirm
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
 - NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
 - dot11wdi/NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NdisWdiIdleNotificationConfirm
---

# NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback function


## -description

Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state. Miniport drivers call this function during an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a> handler function.



This is a control path callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>.

## -parameters

### -param MiniportAdapterHandle 

[in]
The miniport handle.

### -param DeviceIdlePowerState 

[in]
An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_device_power_state">NDIS_DEVICE_POWER_STATE</a> enumeration value that specifies the lowest power state that the network adapter supports for a low-power state transition.

<div class="alert"><b>Note</b>  For USB network adapters, this parameter must be <b>NdisDeviceStateD2</b>.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/network/handling-the-ndis-selective-suspend-idle-notification">Handling the NDIS Selective Suspend Idle Notification</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_device_power_state">NDIS_DEVICE_POWER_STATE</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>
