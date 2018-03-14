---
UID: NC:d3d12umddi.PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021
title: PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021
author: windows-driver-content
description: The pfnShaderCacheGetValueCb callback function gets a shader cache value.
old-location: display\pfnd3d12ddi_shadercachegetvalue_cb_0021.htm
old-project: display
ms.assetid: EFC9E2D0-1995-4FE9-840C-7B33081AEF2F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021, d3d12umddi/pfnShaderCacheGetValueCb, display.pfnd3d12ddi_shadercachegetvalue_cb_0021, pfnShaderCacheGetValueCb, pfnShaderCacheGetValueCb callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnShaderCacheGetValueCb
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 callback


## -description


The <i>pfnShaderCacheGetValueCb</i> callback function gets a shader cache value. 


## -prototype


````
PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 pfnShaderCacheGetValueCb;

HRESULT APIENTRY CALLBACK * pfnShaderCacheGetValueCb(
                  D3D12DDI_HRTDEVICE              hRTDevice,
                  D3D12DDI_HRTPIPELINESTATE       hRTPSO,
  _In_            D3D12DDI_SHADERCACHE_HASH       *pPrecomputedHash,
  _In_      const _reads_bytes_(KeyLen) void      *pKey,
                  SIZE_T                          KeyLen,
  _Out_opt_       _writes_bytes_(*pValueLen) void *pValue,
  _Inout_         SIZE_T                          *pValueLen
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


### -param *pValue [out, optional]

A pointer to an output value. 


### -param *pValueLen [in, out]

The length of the output value.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Access this callback by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md">D3D12DDI_SHADERCACHE_CALLBACKS_0021</a> structure.




## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md">D3D12DDI_SHADERCACHE_CALLBACKS_0021</a>



 

 


