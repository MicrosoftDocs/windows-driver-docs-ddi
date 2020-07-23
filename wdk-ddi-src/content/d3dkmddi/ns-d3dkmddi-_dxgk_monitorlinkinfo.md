---
UID: NS:d3dkmddi._DXGK_MONITORLINKINFO
title: _DXGK_MONITORLINKINFO (d3dkmddi.h)
description: This structure was defined in WDDM 2.1, however the usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO.
old-location: display\dxgk_monitorlinkinfo.htm

ms.assetid: 4A22CC69-F529-4D0B-BF00-877468E29429
ms.date: 04/16/2018
keywords: ["_DXGK_MONITORLINKINFO structure"]
ms.keywords: DXGK_MONITORLINKINFO, DXGK_MONITORLINKINFO structure [Display Devices], PDXGK_MONITORLINKINFO, PDXGK_MONITORLINKINFO structure pointer [Display Devices], _DXGK_MONITORLINKINFO, d3dkmddi/DXGK_MONITORLINKINFO, d3dkmddi/PDXGK_MONITORLINKINFO, display.dxgk_monitorlinkinfo
f1_keywords:
 - "d3dkmddi/DXGK_MONITORLINKINFO"
 - "DXGK_MONITORLINKINFO"
req.header: d3dkmddi.h
req.include-header:
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_MONITORLINKINFO
targetos: Windows
tech.root: display
req.typenames: DXGK_MONITORLINKINFO
---

# _DXGK_MONITORLINKINFO structure


## -description

Describes usage hints for the driver and capabilities for driving a monitor that is connected to a particular target, which does not depend on the current display configuration and can therefore be assumed for the lifetime of the connection. This structure was defined in WDDM 2.1.


## -struct-fields




### -field UsageHints

[in] Hints to the driver on the intended usage of the display device. See [_DXGK_MONITORLINKINFO_USAGEHINTS](../d3dkmdt/ns-d3dkmdt-_dxgk_monitorlinkinfo_usagehints.md).


### -field Capabilities

[out] Flags which describe the capabilities for driving the monitor. See [_DXGK_MONITORLINKINFO_CAPABILITIES structure](../d3dkmdt/ns-d3dkmdt-_dxgk_monitorlinkinfo_capabilities.md).


### -field DitheringSupport

[out] A D3DKMDT_WIRE_FORMAT_AND_PREFERENCE field containing the flags for each wire-format. The driver should set the wire-format bit for each format where the driver and hardware supports dithering beneficial to image quality when the source pixel format contains is higher precision that than the wire-format.

## -remarks

The usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO.  In order to allow the same capabilities structure to be reused in DXGK_QUERYINTEGRATEDDISPLAYOUT, the nested definitions have been extracted into their own structures.

Mode enumeration is typically required to discover if the capability is supported in a particular display configuration. But if the capability is not supported, then mode enumeration is unnecessary.
