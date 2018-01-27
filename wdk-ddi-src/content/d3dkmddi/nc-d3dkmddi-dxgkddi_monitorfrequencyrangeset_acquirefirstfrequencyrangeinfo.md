---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO
title: DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO
author: windows-driver-content
description: The DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO function returns the first frequency range descriptor in a specified monitor frequency range set object.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfnacquirefirstfrequencyrangei.htm
old-project: display
ms.assetid: 08bf8212-4cab-48ba-b9fc-fca2bb4251ff
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_monitorfrequencyrangeset_interface_pfnacquirefirstfrequencyrangei, pfnAcquireFirstFrequencyRangeInfo callback function [Display Devices], pfnAcquireFirstFrequencyRangeInfo, DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO, DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO, d3dkmddi/pfnAcquireFirstFrequencyRangeInfo, VidPnFunctions_63ff519a-3c48-4c80-95a0-35009a532ac0.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	D3dkmddi.h
apiname: 
-	pfnAcquireFirstFrequencyRangeInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO callback


## -description


The <b>DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO</b> function returns the first frequency range descriptor in a specified monitor frequency range set object.


## -prototype


````
NTSTATUS pfnAcquireFirstFrequencyRangeInfo(
  _In_  const D3DKMDT_HMONITORFREQUENCYRANGESET hMonitorFrequencyRangeSet,
  _Out_ const D3DKMDT_MONITOR_FREQUENCY_RANGE   ppFirstMonitorFrequencyRangeInfo
);
````


## -parameters




### -param hMonitorFrequencyRangeSet [in]

[in] A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md">pfnGetMonitorFrequencyRangeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param ppFirstMonitorFrequencyRangeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_frequency_range.md">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure.


## -returns


The <b>pfnAcquireFirstFrequencyRangeInfo</b> function returns one of the following values.
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
The function successfully returned the first frequency range descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DATASET_IS_EMPTY</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded, but there were no frequency range descriptors in the set.

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

You can obtain all the descriptors in a monitor frequency range set by calling <b>pfnAcquireFirstFrequencyRangeInfo</b> and then making a sequence of calls to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo.md">pfnAcquireNextFrequencyRangeInfo</a>.


