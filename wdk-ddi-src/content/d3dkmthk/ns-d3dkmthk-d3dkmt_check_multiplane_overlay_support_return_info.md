---
UID: NS:d3dkmthk.D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
title: D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO (d3dkmthk.h)
description: Structure to check multiplane overlay support return info.
ms.assetid: 83093ae5-fa42-4cb8-8e34-f0545e0f8a2d
ms.date: 10/19/2018
keywords: ["D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO structure"]
ms.keywords: D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO, D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
 - d3dkmthk/D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
dev_langs:
 - c++
---

# D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO structure


## -description

Structure to check multiplane overlay support return info.

## -struct-fields

### -field FailingPlane

The 0 based index of the first plane that could not be supported.

### -field TryAgain

The configuration is not supported due to a transition condition, which should shortly go away.

### -field Reserved

Reserved for internal use.

### -field Value

 
The value used to operate over the other members.

## -remarks

## -see-also

