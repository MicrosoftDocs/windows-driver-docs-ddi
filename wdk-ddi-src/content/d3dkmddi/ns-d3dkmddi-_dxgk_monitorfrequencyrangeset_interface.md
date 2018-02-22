---
UID: NS:d3dkmddi._DXGK_MONITORFREQUENCYRANGESET_INTERFACE
title: "_DXGK_MONITORFREQUENCYRANGESET_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the Monitor Frequency Range Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorfrequencyrangeset_interface.htm
old-project: display
ms.assetid: 4a973ecd-341f-4766-9fed-f56e55f8deae
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3dkmddi/DXGK_MONITORFREQUENCYRANGESET_INTERFACE, DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure [Display Devices], display.dxgk_monitorfrequencyrangeset_interface, DmStructs_7ff19615-df83-4d5e-91c2-8a94a1cfeea3.xml, _DXGK_MONITORFREQUENCYRANGESET_INTERFACE, DXGK_MONITORFREQUENCYRANGESET_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MONITORFREQUENCYRANGESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORFREQUENCYRANGESET_INTERFACE
---

# _DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure


## -description


The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568430">Monitor Frequency Range Set interface</a>, which is implemented by the video present network (VidPN) manager.


## -syntax


````
typedef struct _DXGK_MONITORFREQUENCYRANGESET_INTERFACE {
  DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES          pfnGetNumFrequencyRanges;
  DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO pfnAcquireFirstFrequencyRangeInfo;
  DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO  pfnAcquireNextFrequencyRangeInfo;
  DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO      pfnReleaseFrequencyRangeInfo;
} DXGK_MONITORFREQUENCYRANGESET_INTERFACE;
````


## -struct-fields




### -field pfnGetNumFrequencyRanges

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_getnumfrequencyranges.md">pfnGetNumFrequencyRanges</a> function.


### -field pfnAcquireFirstFrequencyRangeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo.md">pfnAcquireFirstFrequencyRangeInfo</a> function.


### -field pfnAcquireNextFrequencyRangeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo.md">pfnAcquireNextFrequencyRangeInfo</a> function.


### -field pfnReleaseFrequencyRangeInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_releasefrequencyrangeinfo.md">pfnReleaseFrequencyRangeInfo</a> function.

