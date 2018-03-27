---
UID: NS:d3dkmddi._DXGK_MONITORFREQUENCYRANGESET_INTERFACE
title: "_DXGK_MONITORFREQUENCYRANGESET_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the Monitor Frequency Range Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorfrequencyrangeset_interface.htm
old-project: display
ms.assetid: 4a973ecd-341f-4766-9fed-f56e55f8deae
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_MONITORFREQUENCYRANGESET_INTERFACE, DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure [Display Devices], DmStructs_7ff19615-df83-4d5e-91c2-8a94a1cfeea3.xml, _DXGK_MONITORFREQUENCYRANGESET_INTERFACE, d3dkmddi/DXGK_MONITORFREQUENCYRANGESET_INTERFACE, display.dxgk_monitorfrequencyrangeset_interface
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MONITORFREQUENCYRANGESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORFREQUENCYRANGESET_INTERFACE
---

# _DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure


## -description


The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568430">Monitor Frequency Range Set interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field pfnGetNumFrequencyRanges

A pointer to the <a href="https://msdn.microsoft.com/ba70c191-832f-4dd1-b949-cb47cf736c6e">pfnGetNumFrequencyRanges</a> function.


### -field pfnAcquireFirstFrequencyRangeInfo

A pointer to the <a href="https://msdn.microsoft.com/08bf8212-4cab-48ba-b9fc-fca2bb4251ff">pfnAcquireFirstFrequencyRangeInfo</a> function.


### -field pfnAcquireNextFrequencyRangeInfo

A pointer to the <a href="https://msdn.microsoft.com/b5490af8-ef25-4d5c-9154-08660e3d8780">pfnAcquireNextFrequencyRangeInfo</a> function.


### -field pfnReleaseFrequencyRangeInfo

A pointer to the <a href="https://msdn.microsoft.com/54e3d08b-5f0d-4d98-9b93-e2aec96d3362">pfnReleaseFrequencyRangeInfo</a> function.

