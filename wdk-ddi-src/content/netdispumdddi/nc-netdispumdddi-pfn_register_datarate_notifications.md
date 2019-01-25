---
UID: NC:netdispumdddi.PFN_REGISTER_DATARATE_NOTIFICATIONS
title: PFN_REGISTER_DATARATE_NOTIFICATIONS (netdispumdddi.h)
description: Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current network bandwidth of the Miracast connection.The data type of this function is PFN_REGISTER_DATARATE_NOTIFICATIONS.
old-location: display\registerfordataratenotifications.htm
tech.root: display
ms.assetid: 81500bb9-27f1-4688-b244-37dfd766f3c8
ms.date: 05/10/2018
ms.keywords: PFN_REGISTER_DATARATE_NOTIFICATIONS, PFN_REGISTER_DATARATE_NOTIFICATIONS callback, RegisterForDataRateNotifications, RegisterForDataRateNotifications callback function [Display Devices], display.registerfordataratenotifications, netdispumdddi/RegisterForDataRateNotifications
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	RegisterForDataRateNotifications
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_REGISTER_DATARATE_NOTIFICATIONS callback function


## -description


Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current  network bandwidth of the Miracast connection.The data type of this function is <b>PFN_REGISTER_DATARATE_NOTIFICATIONS</b>.

## -parameters

### -param hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


### -param pNotificationContext [in, optional]

The context that will be passed to the <a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a> function when the Miracast data rate changes.


### -param pfnDataRateNotify [in, optional]

A pointer to the driver routine that will be called when the bit rate of the Miracast network link has changed. See Remarks for more info.

The driver can supply a <b>NULL</b> value to unregister for notifications.


## -returns

If the operating system successfully registers or unregisters the driver for notifications, it returns <b>STATUS_SUCCESS</b>.

Otherwise, these error codes can be returned:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_INVALID_PARAMETER** | One or more parameters are invalid. | 
| **STATUS_NOT_SUPPORTED** | The operating system cannot support quality of service (QoS) notifications, or the call to the function is made outside of the calling thread in which the operating system called [StartMiracastSession](https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29)  or [StopMiracastSession](https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77)  functions. | 
## -remarks

The user-mode driver can optionally call this function to register for automatic calls to data rate notification callback functions once a second.

To unregister from notifications, the driver should supply a value of <b>NULL</b> for the <i>pfnDataRateNotify</i> parameter and for the <b>CurrentBitRate</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a> structure
pointed to by the <i>pWfdConnectionStats</i> parameter when it calls the <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> function. When the operating system receives <b>NULL</b> for both <i>pfnDataRateNotify</i> and <b>CurrentBitRate</b>, it will no longer provide notifications.

Also, if the operating system can no longer provide QoS data, it sets the <i>pDataRateStats</i> parameter to <b>NULL</b> when the <a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a>  function is called.

The function fails if the driver attempts to register while it is already registered, or if it attempts to unregister if it has already unregistered. The function fails if the call is made outside of the calling thread in which the operating system called <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> or <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions.




## -see-also




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a>



<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>



<a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a>
 

 

