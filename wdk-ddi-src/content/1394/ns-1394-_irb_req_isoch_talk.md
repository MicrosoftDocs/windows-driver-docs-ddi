---
UID: NS:1394._IRB_REQ_ISOCH_TALK
title: _IRB_REQ_ISOCH_TALK (1394.h)
description: This structure contains the field necessary to carry out a IsochTalk request.
old-location: ieee\irb_req_isoch_talk.htm
tech.root: IEEE
ms.assetid: B42852F3-BF64-44F8-8D9C-361D623CE35A
ms.date: 02/15/2018
keywords: ["_IRB_REQ_ISOCH_TALK structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_TALK, IEEE.irb_req_isoch_talk, IRB_REQ_ISOCH_TALK, IRB_REQ_ISOCH_TALK structure [Buses], _IRB_REQ_ISOCH_TALK
f1_keywords:
 - "1394/IRB_REQ_ISOCH_TALK"
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
- IRB_REQ_ISOCH_TALK
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_TALK
---

# _IRB_REQ_ISOCH_TALK structure


## -description


This structure contains the field necessary to carry out a IsochTalk request.


## -struct-fields




### -field hResource

Specifies the resource handle to use for this operation. Resources are acquired through the REQUEST_ISOCH_ALLOCATE_RESOURCES request.


### -field fulFlags

Reserved. Drivers should set this to zero.


### -field StartTime

Specifies the cycle time to begin operation. This member is used only if the driver specified the RESOURCE_SYNCH_ON_TIME flag when it allocated the resource handle passed in <b>u.IsochTalk.hResource</b>. (The timing resolution is per isochronous cycle, so the <b>CycleOffset</b> member of <b>StartTime</b> is not used.)


## -remarks



Talking on a channel may begin immediately, or it may be synchronized to an event. If the driver set the RESOURCE_SYNCH_ON_TIME flag on the REQUEST_ISOCH_ALLOCATE_RESOURCES request that returned the resource handle, then the write operation begins on the specified cycle count. Additional synchronization options can be set for each buffer in the ISOCH_DESCRIPTOR structure.

If successful, the request returns a STATUS_SUCCESS value. The call returns immediately, and does not wait for any synchronization events. The bus driver calls the callback the driver provides in ISOCH_DESCRIPTOR to signal that it has finished processing an attached buffer.



