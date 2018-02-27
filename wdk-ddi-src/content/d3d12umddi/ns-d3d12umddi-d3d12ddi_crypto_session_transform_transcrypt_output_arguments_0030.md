---
UID: NS:d3d12umddi.D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030
title: D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030
author: windows-driver-content
description: Crypto session transform transcrypt output arguments.
old-location: display\d3d12ddi-crypto-session-transform-transcrypt-output-arguments-0030.htm
old-project: display
ms.assetid: f1edd7c9-3247-4d87-886d-cfd993483f73
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030 structure [Display Devices], d3d12umddi/D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030, display.d3d12ddi-crypto-session-transform-transcrypt-output-arguments-0030
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
-	D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030
---

# D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030 structure


## -description


Crypto session transform transcrypt output arguments.


## -syntax


````
typedef struct _D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030 {
  BOOL    Enable;
  void *  pIV;
  UINT    IVSize;
} D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030;
````


## -struct-fields




### -field Enable

Enable.


### -field pIV

Initialization vector.


### -field IVSize

Initialization vector size.

