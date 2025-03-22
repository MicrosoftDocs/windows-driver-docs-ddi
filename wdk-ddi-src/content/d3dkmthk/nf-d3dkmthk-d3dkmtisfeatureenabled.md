---
UID: NF:d3dkmthk.D3DKMTIsFeatureEnabled
tech.root: display
title: D3DKMTIsFeatureEnabled
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the D3DKMTIsFeatureEnabled function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTIsFeatureEnabled
f1_keywords:
 - D3DKMTIsFeatureEnabled
 - d3dkmthk/D3DKMTIsFeatureEnabled
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTIsFeatureEnabled
---

# D3DKMTIsFeatureEnabled function (d3dkmthk.h)

## -description

A user-mode client calls **D3DKMTIsFeatureEnabled** to query whether a particular WDDM feature is enabled.

## -parameters

### -param unnamedParam1

[in/out] Pointer to a [**D3DKMT_ISFEATUREENABLED**](ns-d3dkmthk-d3dkmt_isfeatureenabled.md) structure that describes the feature to query.

## -returns

**D3DKMTIsFeatureEnabled** returns STATUS_SUCCESS upon successful completion. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**D3DKMT_ISFEATUREENABLED**](ns-d3dkmthk-d3dkmt_isfeatureenabled.md)
