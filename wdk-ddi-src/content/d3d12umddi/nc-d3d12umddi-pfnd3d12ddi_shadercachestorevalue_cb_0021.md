---
UID: NC:d3d12umddi.PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
title: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 (d3d12umddi.h)
description: The pfnShaderCacheStoreValueCb callback function stores a shader cache value.
old-location: display\pfnd3d12ddi_shadercachestorevalue_cb_0021.htm
ms.assetid: F47C4E6E-4B09-4461-85F6-2E850CE2A2F6
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021, PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback, d3d12umddi/pfnShaderCacheStoreValueCb, display.pfnd3d12ddi_shadercachestorevalue_cb_0021, pfnShaderCacheStoreValueCb, pfnShaderCacheStoreValueCb callback function [Display Devices]
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d12umddi/pfnShaderCacheStoreValueCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - pfnShaderCacheStoreValueCb
product:
 - Windows
---

# PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback function

## -description

The <i>pfnShaderCacheStoreValueCb</i> callback function stores a shader cache value.

## -parameters

### -param hRTDevice

The handle of the device for the driver to use when it calls back into the runtime.

### -param hRTPSO

The handle of a PSO.

### -param pPrecomputedHash

A hash value.

### -param pKey

A pointer to a key.

### -param KeyLen

The length of the key.

### -param pValue

A pointer to an output value.

### -param ValueLen

The length of the output value.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

Access this callback by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021">D3D12DDI_SHADERCACHE_CALLBACKS_0021</a> structure.

