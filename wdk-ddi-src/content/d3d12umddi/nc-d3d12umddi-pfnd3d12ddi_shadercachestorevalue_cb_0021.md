---
UID: NC:d3d12umddi.PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
title: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
author: windows-driver-content
description: The pfnShaderCacheStoreValueCb callback function stores a shader cache value.
old-location: display\pfnd3d12ddi_shadercachestorevalue_cb_0021.htm
old-project: display
ms.assetid: F47C4E6E-4B09-4461-85F6-2E850CE2A2F6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021, PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback, d3d12umddi/pfnShaderCacheStoreValueCb, display.pfnd3d12ddi_shadercachestorevalue_cb_0021, pfnShaderCacheStoreValueCb, pfnShaderCacheStoreValueCb callback function [Display Devices]
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
-	pfnShaderCacheStoreValueCb
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback function


## -description


The <i>pfnShaderCacheStoreValueCb</i> callback function stores a shader cache value. 


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



Access this callback by using the <a href="https://msdn.microsoft.com/EBA976B0-3B44-4482-B1B0-31A84150C056">D3D12DDI_SHADERCACHE_CALLBACKS_0021</a> structure.



