---
UID: NS:d3dukmdt.DXGK_MIRACAST_CHUNK_ID
title: DXGK_MIRACAST_CHUNK_ID
author: windows-driver-content
description: Stores info that identifies a wireless display (Miracast) encode chunk.
old-location: display\dxgk_miracast_chunk_id.htm
old-project: display
ms.assetid: 4D350666-B103-4421-A25A-22A7BF41558E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_MIRACAST_CHUNK_ID union [Display Devices], display.dxgk_miracast_chunk_id, d3dukmdt/DXGK_MIRACAST_CHUNK_ID, DXGK_MIRACAST_CHUNK_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h, D3dkmddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dukmdt.h
apiname:
-	DXGK_MIRACAST_CHUNK_ID
product: Windows
targetos: Windows
req.typenames: DXGK_MIRACAST_CHUNK_ID
---

# DXGK_MIRACAST_CHUNK_ID structure


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
} DXGK_MIRACAST_CHUNK_ID;
````


## -struct-fields




### -field FrameNumber

The number of the encoded Wi-Fi frame.


### -field PartNumber

The frame part number.


### -field Value

Holds a 64-bit value that identifies the encode chunk.

