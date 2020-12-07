---
UID: NS:ucxsstreams._STREAM_INFO
title: _STREAM_INFO (ucxsstreams.h)
description: This structure stores information about a stream associated with a bulk endpoint.
old-location: buses\_stream_info.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["STREAM_INFO structure"]
ms.keywords: "*PSTREAM_INFO, P_STREAM_INFO, P_STREAM_INFO structure pointer [Buses], STREAM_INFO, STREAM_INFO structure [Buses], _STREAM_INFO, buses._stream_info, ucxsstreams/P_STREAM_INFO, ucxsstreams/_STREAM_INFO"
req.header: ucxsstreams.h
req.include-header: Ucxclass.h, Ucxstreams.h
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
req.typenames: STREAM_INFO, *PSTREAM_INFO
f1_keywords:
 - _STREAM_INFO
 - ucxsstreams/_STREAM_INFO
 - PSTREAM_INFO
 - ucxsstreams/PSTREAM_INFO
 - STREAM_INFO
 - ucxsstreams/STREAM_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxsstreams.h
api_name:
 - STREAM_INFO
---

# _STREAM_INFO structure


## -description

This structure stores information about a stream associated with a bulk endpoint.

## -struct-fields

### -field Size

The size in bytes of this structure.

### -field WdfQueue

A handle to the framework queue object that contains streams.

### -field StreamId

The stream identifier. The open-static streams request obtains stream identifiers that are assigned by the USB driver stack.

