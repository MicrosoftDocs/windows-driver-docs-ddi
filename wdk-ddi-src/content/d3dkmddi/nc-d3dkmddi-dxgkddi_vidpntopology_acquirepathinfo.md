---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO (d3dkmddi.h)
description: The pfnAcquirePathInfo function returns a descriptor of the video present path specified by a video present source and a video present target within a particular VidPN topology.
old-location: display\dxgk_vidpntopology_interface_pfnacquirepathinfo.htm
ms.assetid: 27a03106-a5b5-489c-968a-81b3ea9940cb
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO, DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO callback, VidPnFunctions_fb690a8a-fc98-4f8f-bfe5-14168a5fdb6a.xml, d3dkmddi/pfnAcquirePathInfo, display.dxgk_vidpntopology_interface_pfnacquirepathinfo, pfnAcquirePathInfo, pfnAcquirePathInfo callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- pfnAcquirePathInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO callback function


## -description


The <b>pfnAcquirePathInfo</b> function returns a descriptor of the video present path specified by a video present source and a video present target within a particular VidPN topology.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceId [in]

[in] An integer that identifies a video present source.


### -param VidPnTargetId [in]

[in] An integer that identifies a video present target.


### -param ppVidPnPresentPathInfo

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the requested path.


## -returns



The <b>pfnAcquirePathInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|


## -remarks



When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>.

A path contains a (source, target) pair, and a topology is a collection of paths. This function returns a descriptor for the path, in a specified topology, that contains a specified (source, target) pair.

You can enumerate all the paths that belong to a VidPN topology object by calling <a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a> and then making a sequence of calls to <b>pfnAcquireNextPathInfo</b>.

VidPN source identifiers are assigned by the operating system. <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

VidPN target identifiers are assigned by the display miniport driver. <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a>



<a href="https://msdn.microsoft.com/9f09ac0e-057c-48fb-a246-35e8ed7ddfc2">pfnAcquireNextPathInfo</a>



<a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>
 

 

