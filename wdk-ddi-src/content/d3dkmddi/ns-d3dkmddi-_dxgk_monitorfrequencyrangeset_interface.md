---
UID: NS:d3dkmddi._DXGK_MONITORFREQUENCYRANGESET_INTERFACE
title: _DXGK_MONITORFREQUENCYRANGESET_INTERFACE (d3dkmddi.h)
description: The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the Monitor Frequency Range Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorfrequencyrangeset_interface.htm
ms.assetid: 4a973ecd-341f-4766-9fed-f56e55f8deae
ms.date: 05/10/2018
ms.keywords: DXGK_MONITORFREQUENCYRANGESET_INTERFACE, DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure [Display Devices], DmStructs_7ff19615-df83-4d5e-91c2-8a94a1cfeea3.xml, _DXGK_MONITORFREQUENCYRANGESET_INTERFACE, d3dkmddi/DXGK_MONITORFREQUENCYRANGESET_INTERFACE, display.dxgk_monitorfrequencyrangeset_interface
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_MONITORFREQUENCYRANGESET_INTERFACE"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_MONITORFREQUENCYRANGESET_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MONITORFREQUENCYRANGESET_INTERFACE
---

# _DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure


## -description


The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor Frequency Range Set interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field pfnGetNumFrequencyRanges

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_getnumfrequencyranges">pfnGetNumFrequencyRanges</a> function.


### -field pfnAcquireFirstFrequencyRangeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo">pfnAcquireFirstFrequencyRangeInfo</a> function.


### -field pfnAcquireNextFrequencyRangeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo">pfnAcquireNextFrequencyRangeInfo</a> function.


### -field pfnReleaseFrequencyRangeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_releasefrequencyrangeinfo">pfnReleaseFrequencyRangeInfo</a> function.

