---
UID: NS:ks.KSSTREAM_UVC_METADATATYPE_TIMESTAMP
title: KSSTREAM_UVC_METADATATYPE_TIMESTAMP
author: windows-driver-content
description: The KSSTREAM_UVC_METADATATYPE_TIMESTAMP structure contains USB video class (UVC) clock and timestamp information.
old-location: stream\ksstream_uvc_metadatatype_timestamp.htm
old-project: stream
ms.assetid: FDA0CD47-36D9-4E64-9377-F419A7D788A3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSSTREAM_UVC_METADATATYPE_TIMESTAMP, ,, A, C, D, E, I, K, KSSTREAM_UVC_METADATATYPE_TIMESTAMP, KSSTREAM_UVC_METADATATYPE_TIMESTAMP structure [Streaming Media Devices], M, P, PKSSTREAM_UVC_METADATATYPE_TIMESTAMP, PKSSTREAM_UVC_METADATATYPE_TIMESTAMP structure pointer [Streaming Media Devices], R, S, T, U, V, Y, _, ks/KSSTREAM_UVC_METADATATYPE_TIMESTAMP, ks/PKSSTREAM_UVC_METADATATYPE_TIMESTAMP, stream.ksstream_uvc_metadatatype_timestamp"
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
-	KSSTREAM_UVC_METADATATYPE_TIMESTAMP
product: Windows
targetos: Windows
req.typenames: KSSTREAM_UVC_METADATATYPE_TIMESTAMP, *PKSSTREAM_UVC_METADATATYPE_TIMESTAMP
---

# KSSTREAM_UVC_METADATATYPE_TIMESTAMP structure


## -description


The <b>KSSTREAM_UVC_METADATATYPE_TIMESTAMP</b> structure contains USB video class (UVC) clock and timestamp information.


## -syntax


````
typedef struct {
  ULONG  PresentationTimeStamp;
  ULONG  SourceClockReference;
  union {
    struct {
      USHORT Counter  :11;
      USHORT Reserved  :5;
    };
    USHORT SCRToken;
  };
  USHORT Reserved0;
  ULONG  Reserved1;
} KSSTREAM_UVC_METADATATYPE_TIMESTAMP, *PKSSTREAM_UVC_METADATATYPE_TIMESTAMP;
````


## -struct-fields




### -field PresentationTimeStamp

Specifies the presentation timestamp.


### -field SourceClockReference

Specifies the source clock reference.


### -field Counter

Specifies the source clock reference counter.


### -field Reserved

Reserved.


### -field Reserved0

Reserved.


### -field Reserved1

Reserved.


#### - SCRToken

Specifies the source clock reference token.

