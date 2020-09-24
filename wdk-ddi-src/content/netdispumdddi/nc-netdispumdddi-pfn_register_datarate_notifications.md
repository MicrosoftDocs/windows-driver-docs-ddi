---
UID: NC:netdispumdddi.PFN_REGISTER_DATARATE_NOTIFICATIONS
title: PFN_REGISTER_DATARATE_NOTIFICATIONS (netdispumdddi.h)
description: Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current network bandwidth of the Miracast connection.The data type of this function is PFN_REGISTER_DATARATE_NOTIFICATIONS.
old-location: display\registerfordataratenotifications.htm
tech.root: display
ms.assetid: 81500bb9-27f1-4688-b244-37dfd766f3c8
ms.date: 05/10/2018
keywords: ["PFN_REGISTER_DATARATE_NOTIFICATIONS callback function"]
ms.keywords: PFN_REGISTER_DATARATE_NOTIFICATIONS, PFN_REGISTER_DATARATE_NOTIFICATIONS callback, RegisterForDataRateNotifications, RegisterForDataRateNotifications callback function [Display Devices], display.registerfordataratenotifications, netdispumdddi/RegisterForDataRateNotifications
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - PFN_REGISTER_DATARATE_NOTIFICATIONS
 - netdispumdddi/PFN_REGISTER_DATARATE_NOTIFICATIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Netdispumdddi.h
api_name:
 - RegisterForDataRateNotifications
---

# PFN_REGISTER_DATARATE_NOTIFICATIONS callback function


## -description

Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current  network bandwidth of the Miracast connection.The data type of this function is <b>PFN_REGISTER_DATARATE_NOTIFICATIONS</b>.

## -parameters

### -param hMiracastDeviceHandle 

[in]
A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.

### -param pNotificationContext 

[in, optional]
The context that will be passed to the <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_datarate_notification">pfnDataRateNotify</a> function when the Miracast data rate changes.

### -param pfnDataRateNotify 

[in, optional]
A pointer to the driver routine that will be called when the bit rate of the Miracast network link has changed. See Remarks for more info.

The driver can supply a <b>NULL</b> value to unregister for notifications.

## -returns

If the operating system successfully registers or unregisters the driver for notifications, it returns <b>STATUS_SUCCESS</b>.

Otherwise, these error codes can be returned:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_INVALID_PARAMETER** | One or more parameters are invalid. | 
| **STATUS_NOT_SUPPORTED** | The operating system cannot support quality of service (QoS) notifications, or the call to the function is made outside of the calling thread in which the operating system called [StartMiracastSession](./nc-netdispumdddi-pfn_start_miracast_session.md)  or [StopMiracastSession](./nc-netdispumdddi-pfn_stop_miracast_session.md)  functions. |

## -remarks

The user-mode driver can optionally call this function to register for automatic calls to data rate notification callback functions once a second.

To unregister from notifications, the driver should supply a value of <b>NULL</b> for the <i>pfnDataRateNotify</i> parameter and for the <b>CurrentBitRate</b> member of the <a href="/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_wfd_connection_stats">MIRACAST_WFD_CONNECTION_STATS</a> structure
pointed to by the <i>pWfdConnectionStats</i> parameter when it calls the <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a> function. When the operating system receives <b>NULL</b> for both <i>pfnDataRateNotify</i> and <b>CurrentBitRate</b>, it will no longer provide notifications.

Also, if the operating system can no longer provide QoS data, it sets the <i>pDataRateStats</i> parameter to <b>NULL</b> when the <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_datarate_notification">pfnDataRateNotify</a>  function is called.

The function fails if the driver attempts to register while it is already registered, or if it attempts to unregister if it has already unregistered. The function fails if the call is made outside of the calling thread in which the operating system called <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a> or <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a> functions.

## -see-also

<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_wfd_connection_stats">MIRACAST_WFD_CONNECTION_STATS</a>



<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>



<a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_datarate_notification">pfnDataRateNotify</a>