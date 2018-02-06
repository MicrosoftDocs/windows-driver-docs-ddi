---
UID: NE:d3d12umddi.D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030
title: D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030
author: windows-driver-content
description: The bitstream encryption type.
old-location: display\d3d12ddi-bitstream-encryption-type-0030.htm
old-project: display
ms.assetid: 99eab339-d93c-4afa-95f2-899ceb2e7828
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_CENC_AES_CTR_128, D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_NONE, d3d12umddi/D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_NONE, D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030 enumeration [Display Devices], d3d12umddi/D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030, D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_CENC_AES_CTR_128, D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030, display.d3d12ddi-bitstream-encryption-type-0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030
---

# D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030 enumeration


## -description


The bitstream encryption type.


## -syntax


````
typedef enum _D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030 { 
  D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_NONE,
  D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_CENC_AES_CTR_128
} D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030;
````


## -enum-fields




### -field D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_NONE

Indicates that the bitstream encryption type is undefined.


### -field D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030_CENC_AES_CTR_128

Indicates that the bitstream encryption type is the CENC (Common Encryption Standard) with an AES-CTR 128 bit key.

