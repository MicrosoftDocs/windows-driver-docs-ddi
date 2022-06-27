---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
title: DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET (d3dkmddi.h)
description: The pfnAssignMultisamplingMethodSet function assigns a set of multisampling methods to a particular video present source in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassignmultisamplingmethodset.htm
ms.date: 05/24/2022
keywords: ["DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback function"]
ms.keywords: DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET, DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback, VidPnFunctions_836f1c8f-1690-4be1-9b77-43a7379278bd.xml, d3dkmddi/pfnAssignMultisamplingMethodSet, display.dxgk_vidpn_interface_pfnassignmultisamplingmethodset, pfnAssignMultisamplingMethodSet, pfnAssignMultisamplingMethodSet callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
 - d3dkmddi/DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
product:
 - Windows
---

# DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback function

## -description

The **DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET** function assigns a set of multisampling methods to a particular video-present source in a specified VidPN.

## -parameters

### -param hVidPn [in]

A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling [**DxgkDdiEnumVidPnCofuncModality**](nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md).

### -param VidPnSourceId [in]

An integer that identifies one of the video present sources associated with the VidPN object.

### -param NumMethods [in]

The number of elements in the **pSupportedMethodSet** array.

### -param pSupportedMethodSet [in]

A pointer to an array of [**D3DDDI_MULTISAMPLINGMETHOD**](../d3dukmdt/ns-d3dukmdt-_d3dddi_multisamplingmethod.md) structures, each of which describes a multisampling method.

## -returns

The **DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET** function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE|The identifier supplied in VidPnSourceId was invalid.|
|STATUS_NO_MEMORY|The function failed because it was unable to allocate enough memory.|

This function might also return other error codes that are defined in Ntstatus.h.

## -see-also

[**DxgkDdiEnumVidPnCofuncModality**](nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md)
