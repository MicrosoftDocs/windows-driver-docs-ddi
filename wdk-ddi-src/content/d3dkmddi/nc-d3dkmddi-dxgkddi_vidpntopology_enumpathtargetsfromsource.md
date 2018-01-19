---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE
title: DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE
author: windows-driver-content
description: The pfnEnumPathTargetsFromSource function returns the identifier of one of the video present targets associated with a specified video present source.
old-location: display\dxgk_vidpntopology_interface_pfnenumpathtargetsfromsource.htm
old-project: display
ms.assetid: ca925b3c-8141-419d-99a1-43764ec07315
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: pfnEnumPathTargetsFromSource
req.alt-loc: d3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE callback



## -description
The <b>pfnEnumPathTargetsFromSource</b> function returns the identifier of one of the video present targets associated with a specified video present source.



## -prototype

````
DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE pfnEnumPathTargetsFromSource;

NTSTATUS APIENTRY pfnEnumPathTargetsFromSource(
  _In_  const D3DKMDT_HVIDPNTOPOLOGY           hVidPnTopology,
  _In_  const D3DDDI_VIDEO_PRESENT_SOURCE_ID   VidPnSourceId,
  _In_  const D3DKMDT_VIDPN_PRESENT_PATH_INDEX VidPnPresentPathIndex,
  _Out_       D3DDDI_VIDEO_PRESENT_TARGET_ID   *pVidPnTargetId
)
{ ... }
````


## -parameters

### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceId [in]

[in] An integer that identifies a particular video present source.


### -param VidPnPresentPathIndex [in]

[in] A zero-based index into the set of paths that contain the source identified by <i>VidPnSourceId</i>.


### -param pVidPnTargetId [out]

[out] A pointer to a variable that receives the target identifier.


## -returns
The <b>pfnEnumPathTargetsFromSource</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>The handle supplied in <i>hVidPnTopology </i>was invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer supplied in <i>pVidPnTargetId</i> was in valid.

 


## -remarks
<i>VidPnPresentPathIndex</i> is not an index into the set of all paths in the topology identified by <i>hVidPnTopology</i>. It is an index into a subset of all the paths in the topology: specifically, the subset of all paths that contain the source identified by <i>VidPnSourceId</i>.

To enumerate (in a given topology) all the targets associated with a particular source, perform the following steps.

Call <b>pfnGetNumPathsFromSource</b> to determine the number N of paths that contain the source of interest. Think of those paths as an indexed set with indices 0, 1, ... N - 1.

For each index 0 though N - 1, pass the source identifier and the index to <b>pfnEnumPathTargetsFromSource</b>.

A topology is a collection paths, each of which contains a (source, target) pair. It is possible for a particular source to appear in more than one path. For example, one source can be paired with two distinct targets in the case of a clone view.

VidPN source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

VidPN target identifiers are assigned by the display miniport driver. <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

The D3DKMDT_HVIDPNTOPOLOGY and D3DKMDT_VIDPN_PRESENT_PATH_INDEX data types are defined in <i>D3dkmdt.h</i>.  

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getnumpathsfromsource.md">pfnGetNumPathsFromSource</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getpathsourcefromtarget.md">pfnGetPathSourceFromTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

