---
UID: NC:netdispumdddi.PFN_DATARATE_NOTIFICATION
title: PFN_DATARATE_NOTIFICATION
author: windows-driver-content
description: Called by the operating system to notify the Miracast user-mode driver that the bit rate of the Miracast network link has changed. This function is registered with the operating system when the RegisterForDataRateNotifications function is called.
old-location: display\pfndataratenotify.htm
old-project: display
ms.assetid: 5eb004d1-7cf8-45a3-aad5-2932b1a83bb8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFN_DATARATE_NOTIFICATION, display.pfndataratenotify, netdispumdddi/pfnDataRateNotify, pfnDataRateNotify, pfnDataRateNotify callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	pfnDataRateNotify
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_DATARATE_NOTIFICATION callback


## -description


Called by the operating system to notify the Miracast user-mode driver that the bit rate of the Miracast network link has changed. This function is registered with the operating system when the <a href="https://msdn.microsoft.com/81500bb9-27f1-4688-b244-37dfd766f3c8">RegisterForDataRateNotifications</a> function is called.


## -parameters




### -param context [in]

A  pointer to a context block associated with a display adapter.

The context value is the value the driver passed in its call to the <a href="https://msdn.microsoft.com/81500bb9-27f1-4688-b244-37dfd766f3c8">RegisterForDataRateNotifications</a> function when it registered the <i>pfnDataRateNotify</i> function.


### -param *pDataRateStats [in, optional]

An optional pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265475">MIRACAST_DATARATE_STATS</a> structure that contains info on the audio/video encoder bit rate and failed or retried Wi-Fi frames.

Can be <b>NULL</b> if the network has an error. For more info, see Remarks.


## -returns



Does not return a value.




## -remarks



If data on the quality of service (QoS) of the network connection becomes unavailable, the <i>pDataRateStats</i> parameter will be set to <b>NULL</b>, and this function will not be called again.




## -see-also




<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265475">MIRACAST_DATARATE_STATS</a>



<a href="https://msdn.microsoft.com/81500bb9-27f1-4688-b244-37dfd766f3c8">RegisterForDataRateNotifications</a>
 

 

