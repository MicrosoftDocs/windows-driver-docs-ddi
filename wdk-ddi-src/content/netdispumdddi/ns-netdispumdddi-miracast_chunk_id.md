---
UID: NS:netdispumdddi.MIRACAST_CHUNK_ID
title: MIRACAST_CHUNK_ID
author: windows-driver-content
description: Stores info that identifies a wireless display (Miracast) encode chunk.
old-location: display\miracast_chunk_id.htm
old-project: display
ms.assetid: 30140530-63B6-4FE4-98A4-C6950D7D4D9A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: MIRACAST_CHUNK_ID, MIRACAST_CHUNK_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_CHUNK_ID
req.alt-loc: Netdispumdddi.h
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
req.typenames: MIRACAST_CHUNK_ID
---

# MIRACAST_CHUNK_ID structure



## -description
Stores info that identifies a wireless display (Miracast) encode chunk.



## -syntax

````
typedef union {
  struct {
    UINT64 FrameNumber  :40;
    UINT64 PartNumber  :24;
  };
  UINT64 Value;
} MIRACAST_CHUNK_ID;
````


## -struct-fields

### -field FrameNumber

The number of the encoded Wi-Fi frame.


### -field PartNumber

The frame part number.


### -field Value

Holds a 64-bit value that identifies the encode chunk.


## -remarks
