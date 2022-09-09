---
UID: NC:d3dkmddi.DXGKCB_QUERYFEATURESUPPORT
tech.root: display
title: DXGKCB_QUERYFEATURESUPPORT
ms.date: 09/08/2022
targetos: Windows
description: Learn more about the DXGKCB_QUERYFEATURESUPPORT callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10 version 20H1
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_QUERYFEATURESUPPORT
f1_keywords:
 - DXGKCB_QUERYFEATURESUPPORT
 - d3dkmddi/DXGKCB_QUERYFEATURESUPPORT
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKCB_QUERYFEATURESUPPORT
---

## -description

A kernel-mode display miniport driver (KMD) calls **DXGKCB_QUERYFEATURESUPPORT** to query whether the OS will permit it to enable support for a feature.

## -parameters

### -param unnamedParam1

Pointer to a [**DXGKARGCB_QUERYFEATURESUPPORT**](ns-d3dkmddi-dxgkargcb_queryfeaturesupport.md) structure that contains information about the feature being queried.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

The OS sets the **Enabled** member of [**DXGKARGCB_QUERYFEATURESUPPORT**](ns-d3dkmddi-dxgkargcb_queryfeaturesupport.md) to TRUE when it permits the driver to enable support for the queried feature. **Enabled** is set to FALSE to instruct the driver to not enable its support for the feature.

The OS's determination of whether to enable a feature is based on a number of factors.

Pre-WDDM 2.9 drivers can call [**DXGKCB_ISFEATUREENABLED**](nc-d3dkmddi-dxgkcb_isfeatureenabled.md) instead.

## -see-also

[**DXGKARGCB_QUERYFEATURESUPPORT**](ns-d3dkmddi-dxgkargcb_queryfeaturesupport.md)
