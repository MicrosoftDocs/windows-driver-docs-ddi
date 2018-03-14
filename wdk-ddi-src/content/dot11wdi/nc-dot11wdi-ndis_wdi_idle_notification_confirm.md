---
UID: NC:dot11wdi.NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
title: NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
author: windows-driver-content
description: Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.
old-location: netvista\ndiswdiidlenotificationconfirm.htm
old-project: netvista
ms.assetid: 39D070BE-FF6F-4EC8-A4E4-DF45C5089AA7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_WDI_IDLE_NOTIFICATION_CONFIRM, NdisWdiIdleNotificationConfirm, NdisWdiIdleNotificationConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiIdleNotificationConfirm, netvista.ndiswdiidlenotificationconfirm
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	NdisWdiIdleNotificationConfirm
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback


## -description


Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state. Miniport drivers call this function during an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_idle_notification.md">MiniportWdiIdleNotification</a> handler function.



This is a control path callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>.


## -prototype


````
NDIS_WDI_IDLE_NOTIFICATION_CONFIRM NdisWdiIdleNotificationConfirm;

VOID NdisWdiIdleNotificationConfirm(
  _In_ NDIS_HANDLE             MiniportAdapterHandle,
  _In_ NDIS_DEVICE_POWER_STATE DeviceIdlePowerState
)
{ ... }
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


### -param DeviceIdlePowerState [in]

An <a href="..\ntddndis\ne-ntddndis-_ndis_device_power_state.md">NDIS_DEVICE_POWER_STATE</a> enumeration value that specifies the lowest power state that the network adapter supports for a low-power state transition.

<div class="alert"><b>Note</b>  For USB network adapters, this parameter must be <b>NdisDeviceStateD2</b>.</div>
<div> </div>

## -returns



This callback function does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/02D13260-5816-4621-8527-E1E79C9AE975">Handling the NDIS Selective Suspend Idle Notification</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_device_power_state.md">NDIS_DEVICE_POWER_STATE</a>



 

 


