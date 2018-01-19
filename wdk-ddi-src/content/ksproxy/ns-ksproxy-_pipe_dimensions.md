---
UID: NS:ksproxy._PIPE_DIMENSIONS
title: _PIPE_DIMENSIONS
author: windows-driver-content
description: The PIPE_DIMENSIONS structure is for proxy use and not recommended for application use. PIPE_DIMENSIONS contains information that describes the compression/expansion ratio of frames on various pins related to a pipe.
old-location: stream\pipe_dimensions.htm
old-project: stream
ms.assetid: 0a919dd8-a266-42c8-8f97-3314a5d52f4f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _PIPE_DIMENSIONS, *PPIPE_DIMENSIONS, PIPE_DIMENSIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PIPE_DIMENSIONS
req.alt-loc: ksproxy.h
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
req.typenames: *PPIPE_DIMENSIONS, PIPE_DIMENSIONS
---

# _PIPE_DIMENSIONS structure



## -description
The PIPE_DIMENSIONS structure is for proxy use and not recommended for application use. PIPE_DIMENSIONS contains information that describes the compression/expansion ratio of frames on various pins related to a pipe.



## -syntax

````
typedef struct _PIPE_DIMENSIONS {
  KS_COMPRESSION AllocatorPin;
  KS_COMPRESSION MaxExpansionPin;
  KS_COMPRESSION EndPin;
} PIPE_DIMENSIONS, *PPIPE_DIMENSIONS;
````


## -struct-fields

### -field AllocatorPin


### -field MaxExpansionPin


### -field EndPin


## -remarks
