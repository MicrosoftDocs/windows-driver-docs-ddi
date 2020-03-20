---
UID: NS:1394._IRB_REQ_ISOCH_DETACH_BUFFERS
title: _IRB_REQ_ISOCH_DETACH_BUFFERS (1394.h)
description: This structure contains the fields required to carry out a IsochDetachBuffers request.
old-location: ieee\irb_req_isoch_detach_buffers.htm
tech.root: IEEE
ms.assetid: 60ED83BD-4AFA-432F-B918-9006815C8D47
ms.date: 02/15/2018
keywords: ["_IRB_REQ_ISOCH_DETACH_BUFFERS structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_DETACH_BUFFERS, IEEE.irb_req_isoch_detach_buffers, IRB_REQ_ISOCH_DETACH_BUFFERS, IRB_REQ_ISOCH_DETACH_BUFFERS structure [Buses], _IRB_REQ_ISOCH_DETACH_BUFFERS
f1_keywords:
 - "1394/IRB_REQ_ISOCH_DETACH_BUFFERS"
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
- IRB_REQ_ISOCH_DETACH_BUFFERS
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_DETACH_BUFFERS
---

# _IRB_REQ_ISOCH_DETACH_BUFFERS structure


## -description


This structure contains the fields required to carry out a IsochDetachBuffers request.


## -struct-fields




### -field hResource

Specifies the resource handle to detach buffers from.


### -field nNumberOfDescriptors

Specifies the number of elements in the <b>pIsochDescriptor</b> array.


### -field pIsochDescriptor

Points to an array of ISOCH_DESCRIPTOR structures that describe the buffers to be detached. The device driver should use the same ISOCH_DESCRIPTOR structure for a buffer that it used to attach the buffer.

