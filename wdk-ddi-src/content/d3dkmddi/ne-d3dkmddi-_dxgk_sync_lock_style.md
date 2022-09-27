---
UID: NE:d3dkmddi._DXGK_SYNC_LOCK_STYLE
title: DXGK_SYNC_LOCK_STYLE (d3dkmddi.h)
description: The sync lock style.
ms.date: 08/25/2022
keywords: ["DXGK_SYNC_LOCK_STYLE enumeration"]
ms.keywords: _DXGK_SYNC_LOCK_STYLE, DXGK_SYNC_LOCK_STYLE,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DXGK_SYNC_LOCK_STYLE
targetos: Windows
tech.root: display
ms.custom: 19H1
f1_keywords:
 - _DXGK_SYNC_LOCK_STYLE
 - d3dkmddi/_DXGK_SYNC_LOCK_STYLE
 - DXGK_SYNC_LOCK_STYLE
 - d3dkmddi/DXGK_SYNC_LOCK_STYLE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_SYNC_LOCK_STYLE
 - DXGK_SYNC_LOCK_STYLE
product:
 - Windows
dev_langs:
 - c++
---

# DXGK_SYNC_LOCK_STYLE enumeration

## -description

Used in the call to [**DxgkDdiSetTimingsFromVidPn**](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) to describe the style of display synchronization to be applied.

## -enum-fields

### -field DXGK_SYNC_LOCK_STYLE_NONE

Indicates that this path is not synchronized. If the *Input.SyncLockStyle* value of [**DXGK_SET_TIMING_PATH_INFO**](ns-d3dkmddi-_dxgk_set_timing_path_info.md) is set to this value, then the *Input.SyncLockGroup* should be set to zero.

### -field DXGK_SYNC_LOCK_STYLE_IDENTICAL

Indicates that this path is synchronized with other paths with the *Input.SyncLockGroup* set to the same non-zero value where all the paths have an identical target mode.

## -remarks

The sync styled defined for WDDM 2.4 - WDDM 2.6 do not allow the styles applied within a group to be mixed, since a path with **DXGK_SYNC_LOCK_STYLE_IDENTICAL** can only be synchronized with another path with **DXGK_SYNC_LOCK_STYLE_IDENTICAL**. However, in future releases, sync styles will support and potentially require different styles within a group.

## -see-also

[**DXGK_SET_TIMING_PATH_INFO**](ns-d3dkmddi-_dxgk_set_timing_path_info.md)
