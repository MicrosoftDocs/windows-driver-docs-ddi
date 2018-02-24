---
UID: NC:netdispumdddi.PFN_DATARATE_NOTIFICATION
title: PFN_DATARATE_NOTIFICATION
author: windows-driver-content
description: Called by the operating system to notify the Miracast user-mode driver that the bit rate of the Miracast network link has changed. This function is registered with the operating system when the RegisterForDataRateNotifications function is called.
old-location: display\pfndataratenotify.htm
old-project: display
ms.assetid: 5eb004d1-7cf8-45a3-aad5-2932b1a83bb8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfndataratenotify, pfnDataRateNotify callback function [Display Devices], pfnDataRateNotify, PFN_DATARATE_NOTIFICATION, PFN_DATARATE_NOTIFICATION, netdispumdddi/pfnDataRateNotify
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
-	pfnDataRateNotify
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_DATARATE_NOTIFICATION callback


## -description


Called by the operating system to notify the Miracast user-mode driver that the bit rate of the Miracast network link has changed. This function is registered with the operating system when the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_register_datarate_notifications.md">RegisterForDataRateNotifications</a> function is called.


## -prototype


````
PFN_DATARATE_NOTIFICATION pfnDataRateNotify;

void NTAPI* pfnDataRateNotify(
  _In_     PVOID                   context,
  _In_opt_ MIRACAST_DATARATE_STATS *pDataRateStats
)
{ ... }
````


## -parameters




### -param context [in]

A  pointer to a context block associated with a display adapter.

The context value is the value the driver passed in its call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_register_datarate_notifications.md">RegisterForDataRateNotifications</a> function when it registered the <i>pfnDataRateNotify</i> function.


### -param *pDataRateStats [in, optional]

An optional pointer to a <a href="..\netdispumdddi\ns-netdispumdddi-miracast_datarate_stats.md">MIRACAST_DATARATE_STATS</a> structure that contains info on the audio/video encoder bit rate and failed or retried Wi-Fi frames.

Can be <b>NULL</b> if the network has an error. For more info, see Remarks.


## -returns



Does not return a value.




## -remarks



If data on the quality of service (QoS) of the network connection becomes unavailable, the <i>pDataRateStats</i> parameter will be set to <b>NULL</b>, and this function will not be called again.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_register_datarate_notifications.md">RegisterForDataRateNotifications</a>



<a href="..\netdispumdddi\ns-netdispumdddi-miracast_datarate_stats.md">MIRACAST_DATARATE_STATS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_DATARATE_NOTIFICATION callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

