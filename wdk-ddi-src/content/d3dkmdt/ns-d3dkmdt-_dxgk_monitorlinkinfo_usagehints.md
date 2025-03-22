---
UID: NS:d3dkmdt._DXGK_MONITORLINKINFO_USAGEHINTS
title: DXGK_MONITORLINKINFO_USAGEHINTS (d3dkmdt.h)
description: Learn about the DXGK_MONITORLINKINFO_USAGEHINTS structure.
tech.root: display
ms.date: 05/20/2024
keywords: ["DXGK_MONITORLINKINFO_USAGEHINTS structure"]
ms.keywords: "*PDXGK_MONITORLINKINFO_USAGEHINTS, DXGK_MONITORLINKINFO_USAGEHINTS, DXGK_MONITORLINKINFO_USAGEHINTS union [Display Devices], PDXGK_MONITORLINKINFO_USAGEHINTS, PDXGK_MONITORLINKINFO_USAGEHINTS union pointer [Display Devices], _DXGK_MONITORLINKINFO_USAGEHINTS, d3dkmdt/DXGK_MONITORLINKINFO_USAGEHINTS, d3dkmdt/PDXGK_MONITORLINKINFO_USAGEHINTS, display.dxgk_monitorlinkinfo_usagehints"
req.header: d3dkmdt.h
req.construct-type: structure
req.include-header: D3dkmddi.h
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
targetos: Windows
req.typenames: DXGK_MONITORLINKINFO_USAGEHINTS, *PDXGK_MONITORLINKINFO_USAGEHINTS
f1_keywords:
 - _DXGK_MONITORLINKINFO_USAGEHINTS
 - d3dkmdt/_DXGK_MONITORLINKINFO_USAGEHINTS
 - PDXGK_MONITORLINKINFO_USAGEHINTS
 - d3dkmdt/PDXGK_MONITORLINKINFO_USAGEHINTS
 - DXGK_MONITORLINKINFO_USAGEHINTS
 - d3dkmdt/DXGK_MONITORLINKINFO_USAGEHINTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_MONITORLINKINFO_USAGEHINTS
 - PDXGK_MONITORLINKINFO_USAGEHINTS
 - DXGK_MONITORLINKINFO_USAGEHINTS
---

# DXGK_MONITORLINKINFO_USAGEHINTS structure (d3dkmdt.h)



## -description

The **DXGK_MONITORLINKINFO_USAGEHINTS** structure provides hints to the driver on the intended usage of the display device (monitor).

## -struct-fields

### -field Hidden

When set, *DxgKrnl* will hide this display from Win32 so it cannot be a part of the desktop.

### -field HeadMounted

When set, the monitor is part of a head-mounted display (HMD) device.

### -field Reserved

This value is reserved for system use.

### -field Value

The collective value of the flags as a single value.
