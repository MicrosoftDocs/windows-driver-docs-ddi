---
UID: NE:d3dkmthk._D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
tech.root: display
title: D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
ms.date: 05/13/2021
targetos: Windows
description: D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER enumerates the tier(s) of support provided by the driver for cross-adapter resources.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
 - D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
f1_keywords:
 - _D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
 - d3dkmthk/_D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
 - D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
 - d3dkmthk/D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER
dev_langs:
 - c++
---

## -description

Currently reserved for system use. **D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER** enumerates the tier(s) of support provided by the driver for cross-adapter resources.

## -enum-fields

### -field D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_NONE

The driver does not provide cross-adapter resource support.

### -field D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_COPY

The driver supports copying to and from cross-adapter shared resources.

### -field D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_TEXTURE

The driver supports shader resource views, unordered access views, and render target views of cross-adapter row-major textures.

### -field D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_SCANOUT

The driver supports scan-out of cross-adapter resources.

## -remarks

## -see-also
