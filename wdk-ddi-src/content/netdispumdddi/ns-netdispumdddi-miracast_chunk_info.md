---
UID: NS:netdispumdddi.MIRACAST_CHUNK_INFO
title: MIRACAST_CHUNK_INFO
author: windows-driver-content
description: Contains info about a specified wireless display (Miracast) encode chunk.
old-location: display\miracast_chunk_info.htm
old-project: display
ms.assetid: 7015cbc5-f8d1-4e06-bb02-2706a26877f0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MIRACAST_CHUNK_INFO, MIRACAST_CHUNK_INFO structure [Display Devices], display.miracast_chunk_info, netdispumdddi/MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Netdispumdddi.h
api_name:
-	MIRACAST_CHUNK_INFO
product: Windows
targetos: Windows
req.typenames: MIRACAST_CHUNK_INFO
---

# MIRACAST_CHUNK_INFO structure


## -description


Contains info about a specified wireless display (Miracast) encode chunk.


## -syntax


````
typedef struct {
  MIRACAST_CHUNK_TYPE ChunkType;
  MIRACAST_CHUNK_ID   ChunkId;
  UINT                ProcessingTime;
  UINT                EncodeRate;
} MIRACAST_CHUNK_INFO;
````


## -struct-fields




### -field ChunkType

The type of chunk that is to be processed, specified as a <a href="..\netdispumdddi\ne-netdispumdddi-miracast_chunk_type.md">MIRACAST_CHUNK_TYPE</a> enumeration value.


### -field ChunkId

The identifier for this chunk, of type <a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>.


### -field ProcessingTime

The time, in microseconds, that it took to process this chunk.


### -field EncodeRate

The encode bit rate, in kilobits per second, that the user-mode driver reported for this chunk.


## -see-also

<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>



<a href="..\netdispumdddi\ne-netdispumdddi-miracast_chunk_type.md">MIRACAST_CHUNK_TYPE</a>



 

 


