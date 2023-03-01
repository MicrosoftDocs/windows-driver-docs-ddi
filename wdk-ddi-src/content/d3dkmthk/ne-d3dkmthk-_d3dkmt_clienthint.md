---
UID: NE:d3dkmthk._D3DKMT_CLIENTHINT
title: D3DKMT_CLIENTHINT (d3dkmthk.h)
description: Client hints.
ms.date: 02/28/2023
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

# D3DKMT_CLIENTHINT enumeration

## -description

D3DKMT_CLIENTHINT hints at which client is [creating a device context]((ns-d3dkmthk-_d3dkmt_createcontext.md)).

## -enum-fields

### -field D3DKMT_CLIENTHINT_UNKNOWN:0

The client is unknown.

### -field D3DKMT_CLIENTHINT_OPENGL:1

The client is the OpenGL runtime.

### -field D3DKMT_CLIENTHINT_CDD:2

CDD (Canonical Display Driver). This value is reserved for internal use.

### -field D3DKMT_CLIENTHINT_OPENCL:3

The client is OpenCL (Open Computing Language).

### -field D3DKMT_CLIENTHINT_VULKAN:4

The client is Vulkan.

### -field D3DKMT_CLIENTHINT_CUDA:5

The client is CUDA (Compute Unified Device Architecture).

### -field D3DKMT_CLIENTHINT_RESERVED:6

Reserved.

### -field D3DKMT_CLIENTHINT_DX7:7

The client is the DirectX 7.0 runtime.

### -field D3DKMT_CLIENTHINT_DX8:8

The client is the DirectX 8.0 runtime.

### -field D3DKMT_CLIENTHINT_DX9:9

The client is the DirectX 9.0 runtime.

### -field D3DKMT_CLIENTHINT_DX10:10

The client is the DirectX 10.0 runtime.

### -field D3DKMT_CLIENTHINT_DX11:11

The client is the DirectX 11.0 runtime.

### -field D3DKMT_CLIENTHINT_DX12:12

The client is the DirectX 12.0 runtime.

### -field D3DKMT_CLIENTHINT_9ON12:13

The client is the D3D9On12 mapping layer (DirectX 9 on DirectX 12).

### -field D3DKMT_CLIENTHINT_11ON12:14

The client is the D3D11On12 mapping layer (DirectX 11 on DirectX 12).

### -field D3DKMT_CLIENTHINT_MFT_ENCODE:15

The client is a Media Foundation Transform (MFT).

### -field D3DKMT_CLIENTHINT_GLON12:16

The client is an OpenGL on DirectX 12 mapping layer.

### -field D3DKMT_CLIENTHINT_CLON12:17

The client is an OpenCL on DirectX 12 mapping layer.

### -field D3DKMT_CLIENTHINT_DML_TENSORFLOW:18

The client is TensorFlow.

### -field D3DKMT_CLIENTHINT_ONEAPI_LEVEL0:19

The client is oneAPI Level Zero.

### -field D3DKMT_CLIENTHINT_DML_PYTORCH:20

The client is PyTorch.

### -field D3DKMT_CLIENTHINT_MAX

Maximum enumeration value.

## -see-also

[D3DKMT_CREATECONTEXT](ns-d3dkmthk-_d3dkmt_createcontext.md)
