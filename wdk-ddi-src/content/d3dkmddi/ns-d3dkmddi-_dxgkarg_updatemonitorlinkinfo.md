---
UID: NS:d3dkmddi._DXGKARG_UPDATEMONITORLINKINFO
title: _DXGKARG_UPDATEMONITORLINKINFO (d3dkmddi.h)
description: Contains arguments for the DXGKDDI_UPDATEMONITORLINKINFO callback function.
ms.date: 10/19/2018
keywords: ["DXGKARG_UPDATEMONITORLINKINFO structure"]
ms.keywords: _DXGKARG_UPDATEMONITORLINKINFO, DXGKARG_UPDATEMONITORLINKINFO, *INOUT_PDXGKARG_UPDATEMONITORLINKINFO
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_UPDATEMONITORLINKINFO
targetos: Windows
tech.root: display
ms.custom: RS5, 19H1
f1_keywords:
 - _DXGKARG_UPDATEMONITORLINKINFO
 - d3dkmddi/_DXGKARG_UPDATEMONITORLINKINFO
 - DXGKARG_UPDATEMONITORLINKINFO
 - d3dkmddi/DXGKARG_UPDATEMONITORLINKINFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_UPDATEMONITORLINKINFO
 - DXGKARG_UPDATEMONITORLINKINFO
dev_langs:
 - c++
---

# _DXGKARG_UPDATEMONITORLINKINFO structure


## -description

Contains arguments for the [DXGKDDI_UPDATEMONITORLINKINFO](../d3dkmddi/nc-d3dkmddi-dxgkddi_updatemonitorlinkinfo.md) callback function.

## -struct-fields

### -field VideoPresentTargetId

The identifier of a display adapter's video present target.

### -field MonitorLinkInfo

Pointer to a [DXGK_MONITORLINKINFO](../d3dkmddi/ns-d3dkmddi-_dxgk_monitorlinkinfo.md) structure, which the driver must fill to describe the capabilities of the monitor over the link through which it has been attached.

## -remarks

## -see-also

