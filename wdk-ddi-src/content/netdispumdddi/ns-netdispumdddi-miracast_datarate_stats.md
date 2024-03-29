---
UID: NS:netdispumdddi.MIRACAST_DATARATE_STATS
title: MIRACAST_DATARATE_STATS (netdispumdddi.h)
description: Contains info used in the wireless display (Miracast) pfnDataRateNotify function about the audio/video encoder bit rate and failed or retried Wi-Fi frames.
old-location: display\miracast_datarate_stats.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["MIRACAST_DATARATE_STATS structure"]
ms.keywords: MIRACAST_DATARATE_STATS, MIRACAST_DATARATE_STATS structure [Display Devices], display.miracast_datarate_stats, netdispumdddi/MIRACAST_DATARATE_STATS
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
targetos: Windows
req.typenames: MIRACAST_DATARATE_STATS
f1_keywords:
 - MIRACAST_DATARATE_STATS
 - netdispumdddi/MIRACAST_DATARATE_STATS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Netdispumdddi.h
api_name:
 - MIRACAST_DATARATE_STATS
---

# MIRACAST_DATARATE_STATS structure


## -description

Contains info used in the wireless display (Miracast) <a href="/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_datarate_notification">pfnDataRateNotify</a> function about the audio/video encoder bit rate and failed or retried Wi-Fi frames.

## -struct-fields

### -field EncoderBitRate

The bit rate, in bits per second, that the operating system recommends that the audio/video encoder uses.

### -field CurrentMaxTxDataRate

The theoretical maximum speed, in bits per second, reported by the Wi-Fi driver.

### -field TransmittedFrameCount

The total number of Wi-Fi frames that were sent with zero retries since the previous time step.

### -field FailedFrameCount

The total number of Wi-Fi frames that exhausted the maximum number of retries since the previous time step.

### -field RetriedFrameCount

The total number of Wi-Fi frames that succeeded after a single retry since the previous time step.

### -field MultipleRetryFrameCount

The total number of Wi-Fi frames that succeeded after more than one retry since the previous time step.

