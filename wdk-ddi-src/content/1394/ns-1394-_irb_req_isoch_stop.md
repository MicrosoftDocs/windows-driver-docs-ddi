---
UID: NS:1394._IRB_REQ_ISOCH_STOP
title: _IRB_REQ_ISOCH_STOP (1394.h)
description: This structure contains the field necessary to carry out a IsochStop request.
old-location: ieee\irb_req_isoch_stop.htm
tech.root: IEEE
ms.assetid: 1400FAC6-DD4E-4E8E-A0ED-C59B700F0672
ms.date: 02/15/2018
keywords: ["_IRB_REQ_ISOCH_STOP structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_STOP, IEEE.irb_req_isoch_stop, IRB_REQ_ISOCH_STOP, IRB_REQ_ISOCH_STOP structure [Buses], _IRB_REQ_ISOCH_STOP
f1_keywords:
 - "1394/IRB_REQ_ISOCH_STOP"
 - "IRB_REQ_ISOCH_STOP"
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
- IRB_REQ_ISOCH_STOP
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_STOP
---

# _IRB_REQ_ISOCH_STOP structure


## -description


This structure contains the field necessary to carry out a IsochStop request.


## -struct-fields




### -field hResource

Specifies the resource handle for the channel on which to stop isochronous operations. 


### -field fulFlags

Reserved. Device drivers should set this member to zero.

