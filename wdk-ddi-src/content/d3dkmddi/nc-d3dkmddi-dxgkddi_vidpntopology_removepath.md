---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH
title: DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH
author: windows-driver-content
description: The pfnRemovePath function removes a video present path to a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnremovepath.htm
old-project: display
ms.assetid: 463973e0-c443-417a-86ff-0b78773d40cc
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
req.alt-api: pfnRemovePath
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

# DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH callback



## -description
The <b>pfnRemovePath</b> function removes a video present path to a specified VidPN topology object.



## -prototype

````
DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH pfnRemovePath;

NTSTATUS APIENTRY pfnRemovePath(
  _In_ const D3DKMDT_HVIDPNTOPOLOGY         hVidPnTopology,
  _In_ const D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
  _In_ const D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId
)
{ ... }
````


## -parameters

### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceId [in]

[in] An integer that identifies a VidPN source path.


### -param VidPnTargetId [in]

[in] An integer that identifies a VidPN target path.


## -returns
The <b>pfnRemovePath</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The specified video present path has been successfully removed from this VidPN topology object.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>The VidPN source identifier supplied in <i>VidPnSourceId </i>is invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET</b></dt>
</dl>The VidPN target identifier supplied in <i>VidPnTargetId </i>is invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>The handle supplied in <i>hVidPnTopology </i>is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The path cannot be removed in the context of the current DDI call.

 


## -remarks
The D3DKMDT_HVIDPNTOPOLOGY data type is defined in<i> D3dkmdt.h</i>.</p>