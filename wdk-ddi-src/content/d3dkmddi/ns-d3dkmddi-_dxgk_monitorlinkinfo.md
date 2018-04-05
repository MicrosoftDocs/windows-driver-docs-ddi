---
UID: NS:d3dkmddi._DXGK_MONITORLINKINFO
title: "_DXGK_MONITORLINKINFO"
author: windows-driver-content
description: This structure was defined in WDDM 2.1, however the usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO.
old-location: display\dxgk_monitorlinkinfo.htm
old-project: display
ms.assetid: 4A22CC69-F529-4D0B-BF00-877468E29429
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_MONITORLINKINFO, DXGK_MONITORLINKINFO structure [Display Devices], PDXGK_MONITORLINKINFO, PDXGK_MONITORLINKINFO structure pointer [Display Devices], _DXGK_MONITORLINKINFO, d3dkmddi/DXGK_MONITORLINKINFO, d3dkmddi/PDXGK_MONITORLINKINFO, display.dxgk_monitorlinkinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MONITORLINKINFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_MONITORLINKINFO
---

# _DXGK_MONITORLINKINFO structure


## -description


This structure was defined in WDDM 2.1, however the usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO.  In order to allow the same capabilities structure to be reused in DXGK_QUERYINTEGRATEDDISPLAYOUT, the nested definitions have been extracted into their own structures.


## -struct-fields




### -field UsageHints

Hints to the driver on the intended usage of the display device.


### -field Capabilities

Flags which describe the capabilities for driving the monitor.

