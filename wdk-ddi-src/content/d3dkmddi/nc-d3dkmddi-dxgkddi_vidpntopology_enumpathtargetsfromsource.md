---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE
title: DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE
author: windows-driver-content
description: The pfnEnumPathTargetsFromSource function returns the identifier of one of the video present targets associated with a specified video present source.
old-location: display\dxgk_vidpntopology_interface_pfnenumpathtargetsfromsource.htm
old-project: display
ms.assetid: ca925b3c-8141-419d-99a1-43764ec07315
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE, VidPnFunctions_1d5b570a-a3c6-444f-884f-cbd7228f64c9.xml, d3dkmddi/pfnEnumPathTargetsFromSource, display.dxgk_vidpntopology_interface_pfnenumpathtargetsfromsource, pfnEnumPathTargetsFromSource, pfnEnumPathTargetsFromSource callback function [Display Devices]
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
-	pfnEnumPathTargetsFromSource
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE callback


## -description


The <b>pfnEnumPathTargetsFromSource</b> function returns the identifier of one of the video present targets associated with a specified video present source.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceId [in]

[in] An integer that identifies a particular video present source.


### -param VidPnPresentPathIndex [in]

[in] A zero-based index into the set of paths that contain the source identified by <i>VidPnSourceId</i>.


### -param pVidPnTargetId [out]

[out] A pointer to a variable that receives the target identifier.


## -returns



The <b>pfnEnumPathTargetsFromSource</b> function returns one of the following values:

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
The pointer supplied in <i>pVidPnTargetId</i> was in valid.

</td>
</tr>
</table>
 




## -remarks



<i>VidPnPresentPathIndex</i> is not an index into the set of all paths in the topology identified by <i>hVidPnTopology</i>. It is an index into a subset of all the paths in the topology: specifically, the subset of all paths that contain the source identified by <i>VidPnSourceId</i>.

To enumerate (in a given topology) all the targets associated with a particular source, perform the following steps.

Call <b>pfnGetNumPathsFromSource</b> to determine the number N of paths that contain the source of interest. Think of those paths as an indexed set with indices 0, 1, ... N - 1.

For each index 0 though N - 1, pass the source identifier and the index to <b>pfnEnumPathTargetsFromSource</b>.

A topology is a collection paths, each of which contains a (source, target) pair. It is possible for a particular source to appear in more than one path. For example, one source can be paired with two distinct targets in the case of a clone view.

VidPN source identifiers are assigned by the operating system. <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

VidPN target identifiers are assigned by the display miniport driver. <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

The D3DKMDT_HVIDPNTOPOLOGY and D3DKMDT_VIDPN_PRESENT_PATH_INDEX data types are defined in <i>D3dkmdt.h</i>.  

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/6c5ee84d-e106-47fc-88bd-b184e9cdd561">pfnGetNumPathsFromSource</a>



<a href="https://msdn.microsoft.com/c3e7b025-2382-4a81-8d78-9333b62b556a">pfnGetPathSourceFromTarget</a>
 

 

