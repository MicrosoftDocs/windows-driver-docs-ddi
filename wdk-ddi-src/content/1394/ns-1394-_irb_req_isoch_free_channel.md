---
UID: NS:1394._IRB_REQ_ISOCH_FREE_CHANNEL
title: _IRB_REQ_ISOCH_FREE_CHANNEL (1394.h)
description: This structure contains the fields required to carry out a IsochFreeChannel request.
old-location: ieee\irb_req_isoch_free_channel.htm
tech.root: IEEE
ms.assetid: 949D165B-1F42-40EA-B050-38847E14B968
ms.date: 02/15/2018
keywords: ["_IRB_REQ_ISOCH_FREE_CHANNEL structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_FREE_CHANNEL, IEEE.irb_req_isoch_free_channel, IRB_REQ_ISOCH_FREE_CHANNEL, IRB_REQ_ISOCH_FREE_CHANNEL structure [Buses], _IRB_REQ_ISOCH_FREE_CHANNEL
f1_keywords:
 - "1394/IRB_REQ_ISOCH_FREE_CHANNEL"
 - "IRB_REQ_ISOCH_FREE_CHANNEL"
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
- IRB_REQ_ISOCH_FREE_CHANNEL
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_FREE_CHANNEL
---

# _IRB_REQ_ISOCH_FREE_CHANNEL structure


## -description


This structure contains the fields required to carry out a IsochFreeChannel request.


## -struct-fields




### -field nChannel

Specifies which allocated channel to release.


## -remarks



If successful, the bus driver sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS, and the isochronous channel is returned to the pool of available channels.



