---
UID: NS:1394._IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
title: _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH (1394.h)
description: This structure contains the fields necessary for the Bus driver to carry out an IsochSetChannelBandwidth request.
old-location: ieee\irb_req_isoch_set_channel_bandwidth.htm
tech.root: IEEE
ms.assetid: CBEB68C2-549F-4EB6-9AF4-4DCA6749F75D
ms.date: 02/15/2018
ms.keywords: 1394/IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH, IEEE.irb_req_isoch_set_channel_bandwidth, IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH, IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH structure [Buses], _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
ms.topic: struct
f1_keywords:
 - "1394/IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH"
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
- 1394.h
api_name:
- IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
---

# _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH structure


## -description


This structure contains the fields necessary for the Bus driver to carry out an <b>IsochSetChannelBandwidth</b> request.


## -struct-fields




### -field hBandwidth

Bandwidth handle to reset.


### -field nMaxBytesPerFrame

Specifies the new bandwidth for <b>hBandwidth</b>.


### -field nBandwidthUnitsRequired

Specifies a pre-calculated value.


## -remarks



This request does not require the caller to know the bandwidth that was allocated when a handle was generated. REQUEST_ISOCH_SET_CHANNEL_BANDWIDTH can be used to readjust the bandwidth on a bandwidth handle whose bytes per frame setting is unknown. Despite its name, this request does not involve isochronous channels in any way.



