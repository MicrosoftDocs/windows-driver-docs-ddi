---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ADDPATH
title: DXGKDDI_VIDPNTOPOLOGY_ADDPATH
author: windows-driver-content
description: The pfnAddPath function adds a video present path to a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnaddpath.htm
old-project: display
ms.assetid: 893e0be1-aa29-429a-a3ca-a9f19053fd92
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ADDPATH, DXGKDDI_VIDPNTOPOLOGY_ADDPATH callback, VidPnFunctions_9c594989-a5f6-4977-8a1b-0302d30e8df7.xml, d3dkmddi/pfnAddPath, display.dxgk_vidpntopology_interface_pfnaddpath, pfnAddPath, pfnAddPath callback function [Display Devices]
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
-	pfnAddPath
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_VIDPNTOPOLOGY_ADDPATH callback function


## -description


The <b>pfnAddPath</b> function adds a video present path to a specified VidPN topology object.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnPresentPath [in]

[in] A pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the path. The display miniport driver previously obtained this pointer by calling <a href="https://msdn.microsoft.com/2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d">pfnCreateNewPathInfo</a>.


## -returns



The <b>pfnAddPath</b> function returns one of the following values:

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
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The path cannot be removed in the context of the current DDI call.

</td>
</tr>
</table>
 




## -remarks



To add a path to a topology, the display miniport driver performs the following steps.

Call <a href="https://msdn.microsoft.com/2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d">pfnCreateNewPathInfo</a> to obtain a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure allocated by the VidPN manager.

Populate the D3DKMDT_VIDPN_PRESENT_PATH structure with information about the path, including video present source and target identifiers.

Call <b>pfnAddPath</b> to add the path to a topology. 

The VidPN manager allocates a D3DKMDT_VIDPN_PRESENT_PATH structure when you call <b>pfnCreateNewPathInfo</b>. If you add the path described by that structure to a topology, then you do not need to explicitly release the structure; <b>pfnAddPath</b> releases it.

If you obtain a D3DKMDT_VIDPN_PRESENT_PATH structure by calling <b>pfnCreateNewPathInfo</b> and then decide not to add that path to a topology, then you must explicity release the structure by calling <b>pfnReleasePathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in<i> D3dkmdt.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d">pfnCreateNewPathInfo</a>



<a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>
 

 

