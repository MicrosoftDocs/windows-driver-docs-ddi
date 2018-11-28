---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO
title: DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO
author: windows-driver-content
description: The pfnReleaseFrequencyRangeInfo function releases a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfnreleasefrequencyrangeinfo.htm
ms.assetid: 54e3d08b-5f0d-4d98-9b93-e2aec96d3362
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO, DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO callback, VidPnFunctions_3fa4c08c-827e-43ac-bcf2-68293d94cb79.xml, d3dkmddi/pfnReleaseFrequencyRangeInfo, display.dxgk_monitorfrequencyrangeset_interface_pfnreleasefrequencyrangeinfo, pfnReleaseFrequencyRangeInfo, pfnReleaseFrequencyRangeInfo callback function [Display Devices]
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnReleaseFrequencyRangeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO callback function


## -description


The <b>pfnReleaseFrequencyRangeInfo</b> function releases a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546103">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hMonitorFrequencyRangeSet [in]

[in] A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/78b80dbb-af1e-457c-854f-ff0404ab9808">pfnGetMonitorFrequencyRangeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pMonitorFrequencyRangeInfo [in]

[in] A pointer to the D3DKMDT_MONITOR_FREQUENCY_RANGE structure that is to be released.


## -returns



The <b>pfnAcquireNextFrequencyRangeInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_MONITOR_FREQUENCY_RANGE|The frequency range descriptor supplied in pMonitorFrequencyRangeInfo was invalid.|
|STATUS_INVALID_MONITOR_FREQUENCYRANGESET|The handle supplied in hMonitorFrequencyRangeSet was invalid.|



## -remarks



When you have finished using a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that you obtained by calling <a href="https://msdn.microsoft.com/08bf8212-4cab-48ba-b9fc-fca2bb4251ff">pfnAcquireFirstFrequencyRangeInfo</a> or <a href="https://msdn.microsoft.com/b5490af8-ef25-4d5c-9154-08660e3d8780">pfnAcquireNextFrequencyRangeInfo</a>, you must release it by calling <b>pfnReleaseFrequencyRangeInfo</b>.



