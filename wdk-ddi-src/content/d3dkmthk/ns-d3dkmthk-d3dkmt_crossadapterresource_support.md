---
UID: NS:d3dkmthk._D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
tech.root: display
title: D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
ms.date: 05/13/2021
targetos: Windows
description: The D3DKMT_CROSSADAPTERRESOURCE_SUPPORT structure indicates the cross adapter resource support provided by a display driver.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
 - D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
f1_keywords:
 - _D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
 - d3dkmthk/_D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
 - D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
 - d3dkmthk/D3DKMT_CROSSADAPTERRESOURCE_SUPPORT
dev_langs:
 - c++
---

## -description

Currently reserved for system use. The **D3DKMT_CROSSADAPTERRESOURCE_SUPPORT** structure indicates the cross adapter resource support provided by a display driver.

## -struct-fields

### -field SupportTier

A [**D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER**](ne-d3dkmthk-d3dkmt_crossadapterresource_support_tier.md) value that describes the tier(s) of support provided by the driver for cross-adapter resources.

## -remarks

The tiers of support for cross-adapter resources are:

* Copying to and from cross-adapter resources (tier 1)
* Texturing from (tier 2)
* Scan-out (tier 3)

Each higher tier of support must imply and guarantee the support tiers below it. For example, to claim support for scan-out of cross-adapter resources, the driver must also support texturing and copy, too (D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_COPY && D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_TEXTURE &&  D3DKMT_CROSSADAPTERRESOURCE_SUPPORT_TIER_SCANOUT).

## -see-also
