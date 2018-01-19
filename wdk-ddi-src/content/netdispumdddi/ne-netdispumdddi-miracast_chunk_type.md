---
UID: NE:netdispumdddi.MIRACAST_CHUNK_TYPE
title: MIRACAST_CHUNK_TYPE
author: windows-driver-content
description: Specifies the types of wireless display (Miracast) chunk info that is to be processed.
old-location: display\miracast_chunk_type.htm
old-project: display
ms.assetid: 39911172-f916-4ca2-8d98-9d53fbc30807
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: MIRACAST_CHUNK_TYPE, MIRACAST_CHUNK_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_CHUNK_TYPE
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
req.typenames: MIRACAST_CHUNK_TYPE
---

# MIRACAST_CHUNK_TYPE enumeration



## -description
Specifies the types of wireless display (Miracast) chunk info that is to be processed.



## -syntax

````
typedef enum  { 
  MIRACAST_CHUNK_TYPE_UNKNOWN                  = 0,
  MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE   = 1,
  MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE          = 2,
  MIRACAST_CHUNK_TYPE_FRAME_START              = 3,
  MIRACAST_CHUNK_TYPE_FRAME_DROPPED            = 4,
  MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1  = 0x80000000,
  MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2  = 0x80000001,
  MIRACAST_CHUNK_TYPE_ENCODE_FORCE_UINT32      = 0xffffffff
} MIRACAST_CHUNK_TYPE;
````


## -enum-fields

### -field MIRACAST_CHUNK_TYPE_UNKNOWN

An unknown or undefined chunk type.


### -field MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE

Color conversion has completed on the chunk.


### -field MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE

Encoding has completed on the chunk.


### -field MIRACAST_CHUNK_TYPE_FRAME_START

The chunk is at the start of the Wi-Fi frame.


### -field MIRACAST_CHUNK_TYPE_FRAME_DROPPED

The chunk is in a dropped Wi-Fi frame.


### -field MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1

Encoding is driver-defined, of type 1.


### -field MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2

Encoding is driver-defined, of type 2.


### -field MIRACAST_CHUNK_TYPE_ENCODE_FORCE_UINT32

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -remarks
