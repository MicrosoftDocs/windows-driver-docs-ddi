---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_RESOURCES_0074
title: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_RESOURCES_0074
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: 1a56facf-6ba1-4e79-9daf-5100e50b1fe7
tech.root: display
description: Device functions for D3D12 protected resources.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_RESOURCES_0074
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_RESOURCES_0074
f1_keywords:
 - d3d12umddi//D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_RESOURCES_0074
 - D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_RESOURCES_0074
dev_langs:
 - c++
---

## -description

Device functions for D3D12 protected resources.

## -struct-fields

### -field pfnCalcPrivateProtectedResourceSessionSize

Calculate the private protected resource session size.

### -field pfnCreateProtectedResourceSession

Create a protected resource session.

### -field pfnCalcPrivateOpenedProtectedResourceSessionSize

Calculate the private opened protected resource session size.

### -field pfnOpenProtectedResourceSession

Open the protected resource session.

### -field pfnDestroyProtectedResourceSession

Destroy the protected resource session.

## -remarks

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also
