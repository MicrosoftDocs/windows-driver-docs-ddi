---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074
title: PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074 (d3d12umddi.h)
description: Used to calculate the size of a protected resource session.
ms.assetid: da35e754-800d-4c69-ada5-31a2b6794493
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074 callback function"]
ms.keywords: PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074, PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074 entry, PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074, display.pfnd3d12ddi_calcprivateprotectedresourcesessionsize_0074
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0074 callback function

## -description

Used to calculate the size of a protected resource session.

## -parameters

### -param hDrvDevice

Handle to the hardware device being processed.

### -param pArgs

Pointer to a [**D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074**](ns-d3d12umddi-d3d12ddiarg_create_protected_resource_session_0074.md) structure with the arguments used to open a protected resource session.

## -returns

Returns the size of the session in bytes.

## -remarks

The D3D runtime allocates memory for storing the driver's CPU object representing the protected resource session. This method is used to calculate the driver object size.

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0074**](ns-d3d12umddi-d3d12ddiarg_create_protected_resource_session_0074.md)

[**PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0074**](nc-d3d12umddi-pfnd3d12ddi_createprotectedresourcesession_0074.md)
