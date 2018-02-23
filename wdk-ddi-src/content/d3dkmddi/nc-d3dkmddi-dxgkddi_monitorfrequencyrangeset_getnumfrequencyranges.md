---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES
title: DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES
author: windows-driver-content
description: The pfnGetNumFrequencyRanges returns the number of frequency range descriptors in a specified monitor frequency range set object.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfngetnumfrequencyranges.htm
old-project: display
ms.assetid: ba70c191-832f-4dd1-b949-cb47cf736c6e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_monitorfrequencyrangeset_interface_pfngetnumfrequencyranges, pfnGetNumFrequencyRanges callback function [Display Devices], pfnGetNumFrequencyRanges, DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES, DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES, d3dkmddi/pfnGetNumFrequencyRanges, VidPnFunctions_9840ad40-d098-4215-b3da-2de345970fe6.xml
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
-	d3dkmddi.h
apiname:
-	pfnGetNumFrequencyRanges
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES callback


## -description


The <b>pfnGetNumFrequencyRanges</b> returns the number of frequency range descriptors in a specified monitor frequency range set object.


## -prototype


````
DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES pfnGetNumFrequencyRanges;

NTSTATUS APIENTRY pfnGetNumFrequencyRanges(
  _In_  const D3DKMDT_HMONITORFREQUENCYRANGESET hMonitorFrequencyRangeSet,
  _Out_       SIZE_T CONST                      *pNumMonitorFrequencyRanges
)
{ ... }
````


## -parameters




### -param hMonitorFrequencyRangeSet [in]

[in] A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <b>pfnGetMonitorFrequencyRangeSet</b> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>. 


### -param pNumMonitorFrequencyRanges [out]

[out] A pointer to a SIZE_T-typed variable that receives the number of descriptors in the set.


## -returns



The <b>pfnGetNumFrequencyRanges</b> function returns one of the following values.

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
The function succeeded.

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
 



