---
UID: NC:dot11wdi.NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
title: NDIS_WDI_IDLE_NOTIFICATION_CONFIRM
author: windows-driver-content
description: Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.
old-location: netvista\ndiswdiidlenotificationconfirm.htm
tech.root: netvista
ms.assetid: 39D070BE-FF6F-4EC8-A4E4-DF45C5089AA7
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NDIS_WDI_IDLE_NOTIFICATION_CONFIRM, NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback, NdisWdiIdleNotificationConfirm, NdisWdiIdleNotificationConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiIdleNotificationConfirm, netvista.ndiswdiidlenotificationconfirm
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_IDLE_NOTIFICATION_CONFIRM callback function


## -description


Miniport drivers call NdisWdiIdleNotificationConfirm callback function to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state. Miniport drivers call this function during an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's <a href="https://msdn.microsoft.com/BA050C7C-A593-469E-9212-B363F2D2A409">MiniportWdiIdleNotification</a> handler function.



This is a control path callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


### -param DeviceIdlePowerState [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/gg602135">NDIS_DEVICE_POWER_STATE</a> enumeration value that specifies the lowest power state that the network adapter supports for a low-power state transition.

<div class="alert"><b>Note</b>  For USB network adapters, this parameter must be <b>NdisDeviceStateD2</b>.</div>
<div> </div>

## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/02D13260-5816-4621-8527-E1E79C9AE975">Handling the NDIS Selective Suspend Idle Notification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg602135">NDIS_DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>
 

 

