---
UID: NS:1394._IRB_REQ_ISOCH_ALLOCATE_CHANNEL
title: _IRB_REQ_ISOCH_ALLOCATE_CHANNEL (1394.h)
description: This structure contains the fields necessary in order for the 1394 bus driver to carry out an IsochAllocateChannel request.
old-location: ieee\irb_req_isoch_allocate_channel.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IRB_REQ_ISOCH_ALLOCATE_CHANNEL structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_ALLOCATE_CHANNEL, IEEE.irb_req_isoch_allocate_channel, IRB_REQ_ISOCH_ALLOCATE_CHANNEL, IRB_REQ_ISOCH_ALLOCATE_CHANNEL structure [Buses], _IRB_REQ_ISOCH_ALLOCATE_CHANNEL
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
req.typenames: IRB_REQ_ISOCH_ALLOCATE_CHANNEL
f1_keywords:
 - _IRB_REQ_ISOCH_ALLOCATE_CHANNEL
 - 1394/_IRB_REQ_ISOCH_ALLOCATE_CHANNEL
 - IRB_REQ_ISOCH_ALLOCATE_CHANNEL
 - 1394/IRB_REQ_ISOCH_ALLOCATE_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_ISOCH_ALLOCATE_CHANNEL
---

# _IRB_REQ_ISOCH_ALLOCATE_CHANNEL structure


## -description

This structure contains the fields necessary in order for the 1394 bus driver to carry out an IsochAllocateChannel request.

## -struct-fields

### -field nRequestedChannel

Specifies the particular channel to allocate, or ISOCH_ANY_CHANNEL for an arbitrary channel.

### -field Channel

Specifies the channel allocated, if the request succeeds.

### -field ChannelsAvailable

A bitmap specifying the available channels. The highest order bit (bit 63) specifies channel 0, the next bit (bit 62) specifies channel 1, and so on.

<div class="alert"><b>Note</b>  Drivers should not rely on this information  because another device may allocate or deallocate channels at any time. The bus driver fills in this member, even if the request fails.</div>
<div> </div>

