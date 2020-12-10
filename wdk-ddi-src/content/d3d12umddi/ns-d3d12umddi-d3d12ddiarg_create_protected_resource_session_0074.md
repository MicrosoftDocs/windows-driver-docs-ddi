---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074
title: D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
tech.root: display
description: Creation arguments for a protected resource session.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074
f1_keywords:
 - D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074
 - d3d12umddi/D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074
dev_langs:
 - c++
---

## -description

Creation arguments for a protected resource session.

## -struct-fields

### -field NodeMask

For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the crypto session applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field ProtectionType

The GUID that represents the protection type. Microsoft defines D3D12DDI_PROTECTED_RESOURCES_SESSION_HARDWARE_PROTECTED. This DDI and corresponding API may be extended by IHV's, but requires Microsoft approval. Allowed GUIDs are controlled by an allow list. Developer mode disables the check to allow for private IHV development.

## -remarks

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074**](nc-d3d12umddi-pfnd3d12ddi_calcprivateprotectedresourcesessionsize_0074.md)

[**PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0074**](nc-d3d12umddi-pfnd3d12ddi_createprotectedresourcesession_0074.md)

