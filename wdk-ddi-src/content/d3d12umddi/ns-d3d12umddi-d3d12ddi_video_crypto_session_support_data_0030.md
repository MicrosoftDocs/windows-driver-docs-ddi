---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030
title: D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030
author: windows-driver-content
description: Video crypto session support data.
old-location: display\d3d12ddi-video-crypto-session-support-data-0030.htm
old-project: display
ms.assetid: 6a1a2c3e-a120-4b5e-bd25-02cb3ab11e9c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030, D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030, display.d3d12ddi-video-crypto-session-support-data-0030
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030
---

# D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030 structure


## -description


Video crypto session support data.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030 {
  UINT                                        NodeIndex;
  GUID                                        DecodeProfile;
  GUID                                        ContentProtectionSystem;
  D3D12DDI_CRYPTO_SESSION_FLAGS_0030          Flags;
  D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030     BitstreamEncryption;
  UINT                                        KeyBaseDataSize;
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030  Support;
} D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030, D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030;
````


## -struct-fields




### -field NodeIndex

Node index.


### -field DecodeProfile

Decode profile.


### -field ContentProtectionSystem

Content protection system.


### -field Flags

Flags.


### -field BitstreamEncryption

Bitstream encryption.


### -field KeyBaseDataSize

Key base data size.


### -field Support

Support.

