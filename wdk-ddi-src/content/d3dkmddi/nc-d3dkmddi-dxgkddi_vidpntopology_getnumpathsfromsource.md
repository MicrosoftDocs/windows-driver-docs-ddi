---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
title: DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
author: windows-driver-content
description: The pfnGetNumPathsFromSource function returns the number of video present paths that contain a specified video present source.
old-location: display\dxgk_vidpntopology_interface_pfngetnumpathsfromsource.htm
old-project: display
ms.assetid: 6c5ee84d-e106-47fc-88bd-b184e9cdd561
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE, VidPnFunctions_6c0bd823-4803-474c-9948-22282c5b1e66.xml, d3dkmddi/pfnGetNumPathsFromSource, display.dxgk_vidpntopology_interface_pfngetnumpathsfromsource, pfnGetNumPathsFromSource, pfnGetNumPathsFromSource callback function [Display Devices]
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
-	d3dkmddi.h
api_name:
-	pfnGetNumPathsFromSource
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE callback


## -description


The <b>pfnGetNumPathsFromSource</b> function returns the number of video present paths that contain a specified video present source.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceId [in]

[in] An integer that identifies a particular video present source.


### -param pNumPathsFromSource [out]

[out] A pointer to a SIZE_T-typed variable that receives the number of paths that contain the specified source.


## -returns



The <b>pfnGetNumPathsFromSource</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pNumPathsFromSource</i> was in valid.

</td>
</tr>
</table>
 




## -remarks



A topology is a collection paths, each of which contains a (source, target) pair. It is possible for a particular source to appear in more than one path. For example, one source can be paired with two distinct targets in the case of a clone view.

VidPN source identifiers are assigned by the operating system. <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/60960774-3f90-4eeb-a408-fa37122f22ea">pfnGetNumPaths</a>
 

 

