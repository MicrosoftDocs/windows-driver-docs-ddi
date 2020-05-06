---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
title: PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 (d3d12umddi.h)
description: Callback to create a graphics kernel protected resource session.
old-location: display\pfnd3d12ddi_create_protected_session_cb_0030.htm
ms.assetid: 64E38759-2863-4481-8A89-6E6263CEFE8B
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function"]
ms.keywords: PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030, PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback, PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030, display.pfnd3d12ddi_create_protected_session_cb_0030
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
product:
 - Windows
---

# PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function

## -description

Callback to create a graphics kernel protected resource session.

## -parameters

### -param hRTDevice

The hardware device being processed.

### -param hRTProtectedSession

The protected session.

### -param pArgs

Pointer to a [**D3D12DDICB_CREATE_PROTECTED_SESSION_0030**](ns-d3d12umddi-d3d12ddicb_create_protected_session_0030.md) structure containing creation arguments for the protected resource session.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -remarks

This function is added to the D3D12DDI_CORELAYER_DEVICECALLBACKS function table. This callback must be called during a call to [**PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0074**](nc-d3d12umddi-pfnd3d12ddi_createprotectedresourcesession_0074.md).

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**D3D12DDICB_CREATE_PROTECTED_SESSION_0030**](ns-d3d12umddi-d3d12ddicb_create_protected_session_0030.md)

[**PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0074**](nc-d3d12umddi-pfnd3d12ddi_createprotectedresourcesession_0074.md)
