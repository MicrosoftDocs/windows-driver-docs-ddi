---
UID: NC:d3d12umddi.PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
title: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
author: windows-driver-content
description: The pfnShaderCacheStoreValueCb callback function stores a shader cache value.
old-location: display\pfnd3d12ddi_shadercachestorevalue_cb_0021.htm
old-project: display
ms.assetid: F47C4E6E-4B09-4461-85F6-2E850CE2A2F6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_shadercachestorevalue_cb_0021, pfnShaderCacheStoreValueCb callback function [Display Devices], pfnShaderCacheStoreValueCb, PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021, PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021, d3d12umddi/pfnShaderCacheStoreValueCb
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnShaderCacheStoreValueCb
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback


## -description


The <i>pfnShaderCacheStoreValueCb</i> callback function stores a shader cache value. 


## -prototype


````
PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 pfnShaderCacheStoreValueCb;

HRESULT APIENTRY CALLBACK * pfnShaderCacheStoreValueCb(
             D3D12DDI_HRTDEVICE           hRTDevice,
             D3D12DDI_HRTPIPELINESTATE    hRTPSO,
  _In_       D3D12DDI_SHADERCACHE_HASH    *pPrecomputedHash,
  _In_ const _reads_bytes_(KeyLen) void   *pKey,
             SIZE_T                       KeyLen,
  _In_ const _reads_bytes_(ValueLen) void *pValue,
             SIZE_T                       ValueLen
)
{ ... }
````


## -parameters




### -param hRTDevice

The handle of the device for the driver to use when it calls back into the runtime.


### -param hRTPSO

The handle of a PSO.


### -param *pPrecomputedHash [in]

A hash value.


### -param *pKey [in]

A pointer to a key.


### -param KeyLen

The length of the key.


### -param *pValue [in]

A pointer to an output value. 


### -param ValueLen

The length of the output value.


## -returns


If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -remarks


Access this callback by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md">D3D12DDI_SHADERCACHE_CALLBACKS_0021</a> structure.


