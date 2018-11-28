---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO
title: DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO
author: windows-driver-content
description: The pfnAcquireNextFrequencyRangeInfo function returns the next frequency range descriptor in a monitor frequency range set, given the current frequency range descriptor.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfnacquirenextfrequencyrangein.htm
ms.assetid: b5490af8-ef25-4d5c-9154-08660e3d8780
ms.date: 05/10/2018
ms.keywords: "(*pfnAcquireNextFrequencyRangeInfo), (*pfnAcquireNextFrequencyRangeInfo) callback function [Display Devices], DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO, DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO callback, VidPnFunctions_13c43302-1e13-4844-8c04-3755f89af477.xml, d3dkmddi/(*pfnAcquireNextFrequencyRangeInfo), display.dxgk_monitorfrequencyrangeset_interface_pfnacquirenextfrequencyrangein"
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
-	D3dkmddi.h
api_name:
-	(*pfnAcquireNextFrequencyRangeInfo)
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO callback function


## -description


The <b>pfnAcquireNextFrequencyRangeInfo</b> function returns the next frequency range descriptor in a monitor frequency range set, given the current frequency range descriptor.


## -parameters




### -param hMonitorFrequencyRangeSet [in]

[in] A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/78b80dbb-af1e-457c-854f-ff0404ab9808">pfnGetMonitorFrequencyRangeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>.


### -param pMonitorFrequencyRangeInfo [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546103">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure that is the current frequency range descriptor. The display miniport driver previously obtained this pointer by calling <a href="https://msdn.microsoft.com/08bf8212-4cab-48ba-b9fc-fca2bb4251ff">pfnAcquireFirstFrequencyRangeInfo</a> or <b>pfnAcquireNextFrequencyRangeInfo</b>.


### -param ppNextMonitorFrequencyRangeInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that is the next frequency range descriptor.


## -returns



The <b>pfnAcquireNextFrequencyRangeInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully returned the next frequency range descriptor.|
|STATUS_GRAPHICS_DATASET_IS_EMPTY|The function succeeded, but there were no more frequency range descriptors in the set.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_INVALID_FREQUENCYRANGE|The frequency range descriptor supplied in pMonitorFrequencyRangeInfo was invalid.|
|STATUS_INVALID_MONITOR_FREQUENCYRANGESET|The handle supplied in hMonitorFrequencyRangeSet was invalid.|
 

This function might also return other error codes defined in <i>Ntstatus.h</i>.




## -remarks



When you have finished using the D3DKMDT_MONITOR_FREQUENCY_RANGE structure, you must release the structure by calling <a href="https://msdn.microsoft.com/54e3d08b-5f0d-4d98-9b93-e2aec96d3362">pfnReleaseFrequencyRangeInfo</a>.

You can obtain all the descriptors in a monitor frequency range set by calling <a href="https://msdn.microsoft.com/08bf8212-4cab-48ba-b9fc-fca2bb4251ff">pfnAcquireFirstFrequencyRangeInfo</a> and then making a sequence of calls to <b>pfnAcquireNextFrequencyRangeInfo</b>.



