---
UID: NC:netdispumdddi.PFN_REGISTER_DATARATE_NOTIFICATIONS
title: PFN_REGISTER_DATARATE_NOTIFICATIONS
author: windows-driver-content
description: Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current network bandwidth of the Miracast connection.The data type of this function is PFN_REGISTER_DATARATE_NOTIFICATIONS.
old-location: display\registerfordataratenotifications.htm
old-project: display
ms.assetid: 81500bb9-27f1-4688-b244-37dfd766f3c8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFN_REGISTER_DATARATE_NOTIFICATIONS, RegisterForDataRateNotifications, RegisterForDataRateNotifications callback function [Display Devices], display.registerfordataratenotifications, netdispumdddi/RegisterForDataRateNotifications
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Netdispumdddi.h
apiname:
-	RegisterForDataRateNotifications
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_REGISTER_DATARATE_NOTIFICATIONS callback


## -description


Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current  network bandwidth of the Miracast connection.The data type of this function is <b>PFN_REGISTER_DATARATE_NOTIFICATIONS</b>.




## -prototype


````
PFN_REGISTER_DATARATE_NOTIFICATIONS RegisterForDataRateNotifications;

NTSTATUS RegisterForDataRateNotifications(
  _In_     HANDLE                    hMiracastDeviceHandle,
  _In_opt_ PVOID                     pNotificationContext,
  _In_opt_ PFN_DATARATE_NOTIFICATION pfnDataRateNotify
)
{ ... }
````


## -parameters




### -param hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.


### -param pNotificationContext [in, optional]

The context that will be passed to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_datarate_notification.md">pfnDataRateNotify</a> function when the Miracast data rate changes.


### -param pfnDataRateNotify [in, optional]

A pointer to the driver routine that will be called when the bit rate of the Miracast network link has changed. See Remarks for more info.

  The driver can supply a <b>NULL</b> value to unregister for notifications.


## -returns



If the operating system successfully registers or unregisters the driver for notifications, it returns <b>STATUS_SUCCESS</b>.

Otherwise, these error codes can be returned:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One or more parameters are invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The operating system cannot support quality of service (QoS) notifications, or the call to the function is made outside of the calling thread in which the operating system called <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a> or <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> functions.

</td>
</tr>
</table>
 




## -remarks



The user-mode driver can optionally call this function to register for automatic calls to data rate notification callback functions once a second.

To unregister from notifications, the driver should supply a value of <b>NULL</b> for the <i>pfnDataRateNotify</i> parameter and for the <b>CurrentBitRate</b> member of the <a href="..\netdispumdddi\ns-netdispumdddi-miracast_wfd_connection_stats.md">MIRACAST_WFD_CONNECTION_STATS</a> structure
pointed to by the <i>pWfdConnectionStats</i> parameter when it calls the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a> function. When the operating system receives <b>NULL</b> for both <i>pfnDataRateNotify</i> and <b>CurrentBitRate</b>, it will no longer provide notifications.

Also, if the operating system can no longer provide QoS data, it sets the <i>pDataRateStats</i> parameter to <b>NULL</b> when the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_datarate_notification.md">pfnDataRateNotify</a>  function is called.

The function fails if the driver attempts to register while it is already registered, or if it attempts to unregister if it has already unregistered. The function fails if the call is made outside of the calling thread in which the operating system called <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a> or <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> functions.




## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_datarate_notification.md">pfnDataRateNotify</a>



<a href="..\netdispumdddi\ns-netdispumdddi-miracast_wfd_connection_stats.md">MIRACAST_WFD_CONNECTION_STATS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_REGISTER_DATARATE_NOTIFICATIONS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

