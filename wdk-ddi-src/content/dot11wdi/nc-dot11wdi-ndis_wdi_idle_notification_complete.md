---
UID: NC:dot11wdi.NDIS_WDI_IDLE_NOTIFICATION_COMPLETE
title: NDIS_WDI_IDLE_NOTIFICATION_COMPLETE (dot11wdi.h)
description: Miniport drivers call NdisWdiIdleNotificationComplete callback function to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's MiniportWdiIdleNotification handler function.
old-location: netvista\ndiswdiidlenotificationcomplete.htm
tech.root: netvista
ms.assetid: 22622545-F92E-4FEE-8F5D-64EC792490C7
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_IDLE_NOTIFICATION_COMPLETE, NDIS_WDI_IDLE_NOTIFICATION_COMPLETE callback, NdisWdiIdleNotificationComplete, NdisWdiIdleNotificationComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiIdleNotificationComplete, netvista.ndiswdiidlenotificationcomplete
ms.topic: callback
f1_keywords:
 - "dot11wdi/NdisWdiIdleNotificationComplete"
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
- NdisWdiIdleNotificationComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_IDLE_NOTIFICATION_COMPLETE callback function


## -description


Miniport drivers call NdisWdiIdleNotificationComplete callback function to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a> handler function.

This is a control path callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/completing-the-ndis-selective-suspend-idle-notification">Completing the NDIS Selective Suspend Idle Notification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>
 

 

