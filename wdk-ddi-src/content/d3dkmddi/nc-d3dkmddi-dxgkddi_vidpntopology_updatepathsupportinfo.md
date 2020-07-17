---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO
title: DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO (d3dkmddi.h)
description: The pfnUpdatePathSupportInfo function updates the transformation and copy protection support of a particular path in a specified VidPN topology.
old-location: display\dxgk_vidpntopology_interface_pfnupdatepathsupportinfo.htm
ms.assetid: affe9ab2-49ef-4284-b441-49c311158827
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO callback function"]
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO, DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO callback, VidPnFunctions_6944a007-1a0a-41fc-b137-92307c532cca.xml, d3dkmddi/pfnUpdatePathSupportInfo, display.dxgk_vidpntopology_interface_pfnupdatepathsupportinfo, pfnUpdatePathSupportInfo, pfnUpdatePathSupportInfo callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/pfnUpdatePathSupportInfo"
 - "pfnUpdatePathSupportInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnUpdatePathSupportInfo
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO callback function

## -description

The <b>pfnUpdatePathSupportInfo</b> function updates the transformation and copy protection support of a particular path in a specified VidPN topology.

## -parameters

### -param i_hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param i_pVidPnPresentPathInfo

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The <b>VidPnSourceId</b> and <b>VidPnTargetId</b> members (taken as a pair) identify the path that is to have its transformation and copy protection support updated. The <b>ContentTransformation</b> and <b>CopyProtection</b> members supply the updated transformation and copy protection support.

## -returns

The <b>pfnUpdatePathSupportInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_TOPOLOGY|The handle supplied in i_hVidPnTopology was invalid.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_ACCESS_DENIED|The path cannot be removed in the context of the current DDI call.|

## -remarks

The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a> function calls <b>pnfUpdatePathSupportInfo</b> to report rotation, scaling, and copy protection support for each of the paths in a topology.

