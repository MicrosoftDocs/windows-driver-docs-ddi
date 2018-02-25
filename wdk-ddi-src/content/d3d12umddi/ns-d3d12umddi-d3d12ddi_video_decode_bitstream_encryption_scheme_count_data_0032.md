---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032
author: windows-driver-content
description: Video decode bitstream encryption scheme count data.
old-location: display\d3d12ddi-video-decode-bitstream-encryption-scheme-count-data-0032.htm
old-project: display
ms.assetid: 0aba733b-a69a-4a8a-a8bc-e934fbbbacbf
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, B, C, D, D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032 structure [Display Devices], E, H, I, M, N, O, P, R, S, T, U, V, Y, _, d3d12umddi/D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032, display.d3d12ddi-video-decode-bitstream-encryption-scheme-count-data-0032"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
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
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032 structure


## -description


Video decode bitstream encryption scheme count data.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032 {
  UINT  NodeIndex;
  GUID  DecodeProfile;
  UINT  BitstreamEncryptionSchemeCount;
} D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032;
````


## -struct-fields




### -field NodeIndex

Node index.


### -field DecodeProfile

Decode profile.


### -field BitstreamEncryptionSchemeCount

Bitstream encryption scheme count.

