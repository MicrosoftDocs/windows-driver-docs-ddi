---
UID: NC:netdispumdddi.PFN_DATARATE_NOTIFICATION
title: PFN_DATARATE_NOTIFICATION (netdispumdddi.h)
description: Called by the operating system to notify the Miracast user-mode driver that the bit rate of the Miracast network link has changed. This function is registered with the operating system when the RegisterForDataRateNotifications function is called.
old-location: display\pfndataratenotify.htm
tech.root: display
ms.assetid: 5eb004d1-7cf8-45a3-aad5-2932b1a83bb8
ms.date: 05/10/2018
keywords: ["PFN_DATARATE_NOTIFICATION callback function"]
ms.keywords: PFN_DATARATE_NOTIFICATION, PFN_DATARATE_NOTIFICATION callback, display.pfndataratenotify, netdispumdddi/pfnDataRateNotify, pfnDataRateNotify, pfnDataRateNotify callback function [Display Devices]
f1_keywords:
 - "netdispumdddi/pfnDataRateNotify"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Netdispumdddi.h
api_name:
- pfnDataRateNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_DATARATE_NOTIFICATION callback function


## -description


Called by the operating system to notify the Miracast user-mode driver that the bit rate of the Miracast network link has changed. This function is registered with the operating system when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_register_datarate_notifications">RegisterForDataRateNotifications</a> function is called.


## -parameters




### -param context [in]

A  pointer to a context block associated with a display adapter.

The context value is the value the driver passed in its call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_register_datarate_notifications">RegisterForDataRateNotifications</a> function when it registered the <i>pfnDataRateNotify</i> function.


### -param *pDataRateStats [in, optional]

An optional pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_datarate_stats">MIRACAST_DATARATE_STATS</a> structure that contains info on the audio/video encoder bit rate and failed or retried Wi-Fi frames.

Can be <b>NULL</b> if the network has an error. For more info, see Remarks.


## -remarks



If data on the quality of service (QoS) of the network connection becomes unavailable, the <i>pDataRateStats</i> parameter will be set to <b>NULL</b>, and this function will not be called again.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_datarate_stats">MIRACAST_DATARATE_STATS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_register_datarate_notifications">RegisterForDataRateNotifications</a>
 

 

