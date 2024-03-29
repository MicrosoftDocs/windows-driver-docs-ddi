---
UID: NC:d3dumddi.PFND3DDDI_UNLOCK2CB
title: PFND3DDDI_UNLOCK2CB (d3dumddi.h)
description: The pfnUnlock2Cb function unlocks an allocation that was locked by a call to the pfnLock2Cb function.
old-location: display\pfnunlock2cb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_UNLOCK2CB callback function"]
ms.keywords: PFND3DDDI_UNLOCK2CB, PFND3DDDI_UNLOCK2CB callback, d3dumddi/pfnUnlock2Cb, display.pfnunlock2cb, pfnUnlock2Cb, pfnUnlock2Cb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_UNLOCK2CB
 - d3dumddi/PFND3DDDI_UNLOCK2CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_UNLOCK2CB
---

# PFND3DDDI_UNLOCK2CB callback function


## -description

The <b>pfnUnlock2Cb</b> function unlocks an allocation that was locked by a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lock2cb">pfnLock2Cb</a> function.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_unlock2">D3DDDICB_UNLOCK2</a> structure that describes the allocation to unlock.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

