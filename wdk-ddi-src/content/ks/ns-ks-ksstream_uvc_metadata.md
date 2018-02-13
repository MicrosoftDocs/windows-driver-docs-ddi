---
UID: NS:ks.KSSTREAM_UVC_METADATA
title: KSSTREAM_UVC_METADATA
author: windows-driver-content
description: The KSSTREAM_UVC_METADATA structure contains start and end of frame timestamp information.
old-location: stream\ksstream_uvc_metadata.htm
old-project: stream
ms.assetid: 99ED5E06-23C7-4B24-BD9B-E6713B1D58D2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSSTREAM_UVC_METADATA, *PKSSTREAM_UVC_METADATA, ks/KSSTREAM_UVC_METADATA, PKSSTREAM_UVC_METADATA structure pointer [Streaming Media Devices], stream.ksstream_uvc_metadata, KSSTREAM_UVC_METADATA structure [Streaming Media Devices], ks/PKSSTREAM_UVC_METADATA, PKSSTREAM_UVC_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSSTREAM_UVC_METADATA
product: Windows
targetos: Windows
req.typenames: "*PKSSTREAM_UVC_METADATA, KSSTREAM_UVC_METADATA"
---

# KSSTREAM_UVC_METADATA structure


## -description


The <b>KSSTREAM_UVC_METADATA</b> structure contains start and end of frame timestamp information.


## -syntax


````
typedef struct {
  KSSTREAM_UVC_METADATATYPE_TIMESTAMP StartOfFrameTimestamp;
  KSSTREAM_UVC_METADATATYPE_TIMESTAMP EndOfFrameTimestamp;
} KSSTREAM_UVC_METADATA, *PKSSTREAM_UVC_METADATA;
````


## -struct-fields




### -field StartOfFrameTimestamp

Contains  start of frame timestamp information.


### -field EndOfFrameTimestamp

Contains end of frame timestamp information.

