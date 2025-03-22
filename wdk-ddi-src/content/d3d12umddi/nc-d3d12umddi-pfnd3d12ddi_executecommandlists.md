---
UID: NC:d3d12umddi.PFND3D12DDI_EXECUTECOMMANDLISTS
tech.root: display
title: PFND3D12DDI_EXECUTECOMMANDLISTS
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_EXECUTECOMMANDLISTS callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll:
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_EXECUTECOMMANDLISTS
f1_keywords:
 - PFND3D12DDI_EXECUTECOMMANDLISTS
 - d3d12umddi/PFND3D12DDI_EXECUTECOMMANDLISTS
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_EXECUTECOMMANDLISTS
---

# PFND3D12DDI_EXECUTECOMMANDLISTS function (d3d12umddi.h)

## -description

UMD's **PFND3D12DDI_EXECUTECOMMANDLISTS** function executes an array of command lists submitted by an application.

## -parameters

### -param unnamedParam1

[in] Handle to the driver's command queue.

### -param Count

[in] Number of command lists in the array that **pCommandLists** points to.

### -param pCommandLists

[in] Pointer to an array of **Count** handles to the command lists (D3D12DDI_HCOMMANDLIST) that need to be executed.

## -remarks

## -see-also
