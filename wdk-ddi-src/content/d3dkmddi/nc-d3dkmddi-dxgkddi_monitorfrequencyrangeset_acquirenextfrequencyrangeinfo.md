---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO
title: DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO
author: windows-driver-content
description: The pfnAcquireNextFrequencyRangeInfo function returns the next frequency range descriptor in a monitor frequency range set, given the current frequency range descriptor.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfnacquirenextfrequencyrangein.htm
old-project: display
ms.assetid: b5490af8-ef25-4d5c-9154-08660e3d8780
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "(*pfnAcquireNextFrequencyRangeInfo), (*pfnAcquireNextFrequencyRangeInfo) callback function [Display Devices], DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO, VidPnFunctions_13c43302-1e13-4844-8c04-3755f89af477.xml, d3dkmddi/(*pfnAcquireNextFrequencyRangeInfo), display.dxgk_monitorfrequencyrangeset_interface_pfnacquirenextfrequencyrangein"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO callback


## -description


The <b>pfnAcquireNextFrequencyRangeInfo</b> function returns the next frequency range descriptor in a monitor frequency range set, given the current frequency range descriptor.


## -prototype


````
NTSTATUS APIENTRY (*pfnAcquireNextFrequencyRangeInfo)(
  _In_  const D3DKMDT_HMONITORFREQUENCYRANGESET     hMonitorFrequencyRangeSet,
  _In_  const D3DKMDT_MONITOR_FREQUENCY_RANGE CONST *pMonitorFrequencyRangeInfo,
  _Out_ const D3DKMDT_MONITOR_FREQUENCY_RANGE       **ppNextMonitorFrequencyRangeInfo
);
````


## -parameters




### -param hMonitorFrequencyRangeSet [in]

[in] A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md">pfnGetMonitorFrequencyRangeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>.


### -param pMonitorFrequencyRangeInfo [in]

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_frequency_range.md">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure that is the current frequency range descriptor. The display miniport driver previously obtained this pointer by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo.md">pfnAcquireFirstFrequencyRangeInfo</a> or <b>pfnAcquireNextFrequencyRangeInfo</b>.


### -param ppNextMonitorFrequencyRangeInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that is the next frequency range descriptor.


## -returns



The <b>pfnAcquireNextFrequencyRangeInfo</b> function returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function successfully returned the next frequency range descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DATASET_IS_EMPTY</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded, but there were no more frequency range descriptors in the set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_FREQUENCYRANGE</b></dt>
</dl>
</td>
<td width="60%">
The frequency range descriptor supplied in <i>pMonitorFrequencyRangeInfo</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_MONITOR_FREQUENCYRANGESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hMonitorFrequencyRangeSet</i> was invalid.

</td>
</tr>
</table>
 

This function might also return other error codes defined in <i>Ntstatus.h</i>.




## -remarks



When you have finished using the D3DKMDT_MONITOR_FREQUENCY_RANGE structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_releasefrequencyrangeinfo.md">pfnReleaseFrequencyRangeInfo</a>.

You can obtain all the descriptors in a monitor frequency range set by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo.md">pfnAcquireFirstFrequencyRangeInfo</a> and then making a sequence of calls to <b>pfnAcquireNextFrequencyRangeInfo</b>.



