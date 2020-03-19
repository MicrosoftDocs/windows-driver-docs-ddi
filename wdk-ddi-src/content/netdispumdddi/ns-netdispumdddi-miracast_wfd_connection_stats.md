---
UID: NS:netdispumdddi.__unnamed_struct_6
title: MIRACAST_WFD_CONNECTION_STATS (netdispumdddi.h)
description: Contains bit rate info on the Wi-Fi Direct connection.
old-location: display\miracast_wfd_connection_stats.htm
tech.root: display
ms.assetid: 3d5dd27f-8d0e-46e8-adbd-139db322cf6e
ms.date: 05/10/2018
keywords: ["MIRACAST_WFD_CONNECTION_STATS structure"]
ms.keywords: MIRACAST_WFD_CONNECTION_STATS, MIRACAST_WFD_CONNECTION_STATS structure [Display Devices], display.miracast_wfd_connection_stats, netdispumdddi/MIRACAST_WFD_CONNECTION_STATS
f1_keywords:
 - "netdispumdddi/MIRACAST_WFD_CONNECTION_STATS"
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- Netdispumdddi.h
api_name:
- MIRACAST_WFD_CONNECTION_STATS
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_WFD_CONNECTION_STATS
---

# MIRACAST_WFD_CONNECTION_STATS structure


## -description


Contains bit rate info on the Wi-Fi Direct connection.


## -struct-fields




### -field CurrentBitRate

The bit rate, in bits per second, that the operating system recommends that the audio/video encoder uses.


### -field LocalMaxBitRate

The maximum bit rate, in bits per second, that the local Wi-Fi Direct hardware can support.


### -field RemoteMaxBitRate

The maximum bit rate, in bits per second, that the Miracast sink hardware can support.

