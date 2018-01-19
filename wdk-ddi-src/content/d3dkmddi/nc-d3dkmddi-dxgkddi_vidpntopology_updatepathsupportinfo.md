---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO
title: DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO
author: windows-driver-content
description: The pfnUpdatePathSupportInfo function updates the transformation and copy protection support of a particular path in a specified VidPN topology.
old-location: display\dxgk_vidpntopology_interface_pfnupdatepathsupportinfo.htm
old-project: display
ms.assetid: affe9ab2-49ef-4284-b441-49c311158827
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
req.alt-api: pfnUpdatePathSupportInfo
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

# DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO callback



## -description
The <b>pfnUpdatePathSupportInfo</b> function updates the transformation and copy protection support of a particular path in a specified VidPN topology.



## -prototype

````
DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO pfnUpdatePathSupportInfo;

NTSTATUS APIENTRY pfnUpdatePathSupportInfo(
  _In_ const D3DKMDT_HVIDPNTOPOLOGY     i_hVidPnTopology,
  _In_ const D3DKMDT_VIDPN_PRESENT_PATH *i_pVidPnPresentPathInfo
)
{ ... }
````


## -parameters

### -param i_hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param i_pVidPnPresentPathInfo [in]

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The <b>VidPnSourceId</b> and <b>VidPnTargetId</b> members (taken as a pair) identify the path that is to have its transformation and copy protection support updated. The <b>ContentTransformation</b> and <b>CopyProtection</b> members supply the updated transformation and copy protection support.


## -returns
The <b>pfnUpdatePathSupportInfo</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_TOPOLOGY</b></dt>
</dl>The handle supplied in <i>i_hVidPnTopology</i> was invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was supplied.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The path cannot be removed in the context of the current DDI call.

 


## -remarks
The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> function calls <b>pnfUpdatePathSupportInfo</b> to report rotation, scaling, and copy protection support for each of the paths in a topology.</p>