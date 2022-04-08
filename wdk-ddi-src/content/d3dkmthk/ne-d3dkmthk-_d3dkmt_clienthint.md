---
UID: NE:d3dkmthk._D3DKMT_CLIENTHINT
title: _D3DKMT_CLIENTHINT (d3dkmthk.h)
description: Client hints.
ms.date: 03/08/2022
keywords: ["D3DKMT_CLIENTHINT enumeration"]
ms.keywords: _D3DKMT_CLIENTHINT, D3DKMT_CLIENTHINT,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DKMT_CLIENTHINT
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_CLIENTHINT
 - d3dkmthk/_D3DKMT_CLIENTHINT
 - D3DKMT_CLIENTHINT
 - d3dkmthk/D3DKMT_CLIENTHINT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CLIENTHINT
 - D3DKMT_CLIENTHINT
dev_langs:
 - c++
---

# _D3DKMT_CLIENTHINT enumeration

## -description

Hints which client is creating a device context.

## -enum-fields

### -field D3DKMT_CLIENTHINT_UNKNOWN

Unknown

### -field D3DKMT_CLIENTHINT_OPENGL

OpenGL

### -field D3DKMT_CLIENTHINT_CDD

CDD (Canonical Display Driver)

### -field D3DKMT_CLIENTHINT_OPENCL

OpenCL

### -field D3DKMT_CLIENTHINT_VULKAN

Vulkan

### -field D3DKMT_CLIENTHINT_CUDA

Cuda

### -field D3DKMT_CLIENTHINT_RESERVED

Reserved

### -field D3DKMT_CLIENTHINT_DX7

DirectX 7

### -field D3DKMT_CLIENTHINT_DX8

DirectX 8

### -field D3DKMT_CLIENTHINT_DX9

DirectX 9

### -field D3DKMT_CLIENTHINT_DX10

DirectX 10

### -field D3DKMT_CLIENTHINT_DX11

DirectX 11

### -field D3DKMT_CLIENTHINT_DX12

DirectX 12

### -field D3DKMT_CLIENTHINT_9ON12

DirectX 9 on DirectX 12

### -field D3DKMT_CLIENTHINT_11ON12

DirectX 11 on DirectX 12

### -field D3DKMT_CLIENTHINT_MFT_ENCODE

Media Foundation transform (MFT) encode

### -field D3DKMT_CLIENTHINT_GLON12

OpenGL on DirectX 12

### -field D3DKMT_CLIENTHINT_CLON12

OpenCL on DirectX 12

### -field D3DKMT_CLIENTHINT_DML_TENSORFLOW

Tensor Flow

### -field D3DKMT_CLIENTHINT_ONEAPI_LEVEL0

oneAPI Level Zero

### -field D3DKMT_CLIENTHINT_MAX

Reserved for internal validation

## -remarks

## -see-also

[D3DKMT_CREATECONTEXT](ns-d3dkmthk-_d3dkmt_createcontext.md)
