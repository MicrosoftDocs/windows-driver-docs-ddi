---
UID: NS:1394._IRB_REQ_ISOCH_ALLOCATE_CHANNEL
title: "_IRB_REQ_ISOCH_ALLOCATE_CHANNEL"
author: windows-driver-content
description: This structure contains the fields necessary in order for the 1394 bus driver to carry out an IsochAllocateChannel request.
old-location: ieee\irb_req_isoch_allocate_channel.htm
old-project: IEEE
ms.assetid: CE38C189-34C7-40FC-81BE-9688AC9A7420
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "_IRB_REQ_ISOCH_ALLOCATE_CHANNEL, 1394/IRB_REQ_ISOCH_ALLOCATE_CHANNEL, IRB_REQ_ISOCH_ALLOCATE_CHANNEL structure [Buses], IRB_REQ_ISOCH_ALLOCATE_CHANNEL, IEEE.irb_req_isoch_allocate_channel"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_ISOCH_ALLOCATE_CHANNEL
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_ALLOCATE_CHANNEL
---

# _IRB_REQ_ISOCH_ALLOCATE_CHANNEL structure


## -description


This structure contains the fields necessary in order for the 1394 bus driver to carry out an IsochAllocateChannel request.


## -syntax


````
typedef struct _IRB_REQ_ISOCH_ALLOCATE_CHANNEL {
  ULONG         nRequestedChannel;
  ULONG         Channel;
  LARGE_INTEGER ChannelsAvailable;
} IRB_REQ_ISOCH_ALLOCATE_CHANNEL;
````


## -struct-fields




### -field nRequestedChannel

Specifies the particular channel to allocate, or ISOCH_ANY_CHANNEL for an arbitrary channel. 


### -field Channel

Specifies the channel allocated, if the request succeeds.


### -field ChannelsAvailable

A bitmap specifying the available channels. The highest order bit (bit 63) specifies channel 0, the next bit (bit 62) specifies channel 1, and so on.

<div class="alert"><b>Note</b>  Drivers should not rely on this information  because another device may allocate or deallocate channels at any time. The bus driver fills in this member, even if the request fails.</div>
<div> </div>
