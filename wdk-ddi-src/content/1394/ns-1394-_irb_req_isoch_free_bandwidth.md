---
UID: NS:1394._IRB_REQ_ISOCH_FREE_BANDWIDTH
title: _IRB_REQ_ISOCH_FREE_BANDWIDTH (1394.h)
description: This structure contains the fields necessary in order for the Bus driver to carry out an IsochFreeBandwidth request.
old-location: ieee\irb_req_isoch_free_bandwidth.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IRB_REQ_ISOCH_FREE_BANDWIDTH structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_FREE_BANDWIDTH, IEEE.irb_req_isoch_free_bandwidth, IRB_REQ_ISOCH_FREE_BANDWIDTH, IRB_REQ_ISOCH_FREE_BANDWIDTH structure [Buses], _IRB_REQ_ISOCH_FREE_BANDWIDTH
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
targetos: Windows
req.typenames: IRB_REQ_ISOCH_FREE_BANDWIDTH
f1_keywords:
 - _IRB_REQ_ISOCH_FREE_BANDWIDTH
 - 1394/_IRB_REQ_ISOCH_FREE_BANDWIDTH
 - IRB_REQ_ISOCH_FREE_BANDWIDTH
 - 1394/IRB_REQ_ISOCH_FREE_BANDWIDTH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_ISOCH_FREE_BANDWIDTH
---

# _IRB_REQ_ISOCH_FREE_BANDWIDTH structure


## -description

This structure contains the fields necessary in order for the Bus driver to carry out an <b>IsochFreeBandwidth</b> request.

## -struct-fields

### -field hBandwidth

Specifies the bandwidth handle to release.

### -field nMaxBytesPerFrameRequested

### -field fulSpeed

### -field BytesPerFrameAvailable

### -field SpeedSelected

### -field nBandwidthUnitsRequired

## -remarks

If successful, the bus driver sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS, and the isochronous bandwidth is returned to the pool of available bandwidth.

A status of STATUS_INVALID_GENERATION also indicates success. 

Do not resend the REQUEST_ISOCH_FREE_BANDWIDTH request in order to release isochronous bandwidth if the request failed with the STATUS_INVALID_GENERATION error code. In that case, it is safe to assume that isochronous bandwidth was released as a result of 1394 bus generation changes.

