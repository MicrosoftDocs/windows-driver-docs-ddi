---
UID: NS:d3dkmddi._DXGKARG_RECOMMENDFUNCTIONALVIDPN
title: _DXGKARG_RECOMMENDFUNCTIONALVIDPN (d3dkmddi.h)
description: The DXGKARG_RECOMMENDFUNCTIONALVIDPN structure contains arguments for the DxgkDdiRecommendFunctionalVidPn function.
old-location: display\dxgkarg_recommendfunctionalvidpn.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_RECOMMENDFUNCTIONALVIDPN structure"]
ms.keywords: DXGKARG_RECOMMENDFUNCTIONALVIDPN, DXGKARG_RECOMMENDFUNCTIONALVIDPN structure [Display Devices], DmStructs_15342273-6bfe-4cee-8f8e-1d89c7683e4b.xml, _DXGKARG_RECOMMENDFUNCTIONALVIDPN, d3dkmddi/DXGKARG_RECOMMENDFUNCTIONALVIDPN, display.dxgkarg_recommendfunctionalvidpn
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGKARG_RECOMMENDFUNCTIONALVIDPN
f1_keywords:
 - _DXGKARG_RECOMMENDFUNCTIONALVIDPN
 - d3dkmddi/_DXGKARG_RECOMMENDFUNCTIONALVIDPN
 - DXGKARG_RECOMMENDFUNCTIONALVIDPN
 - d3dkmddi/DXGKARG_RECOMMENDFUNCTIONALVIDPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_RECOMMENDFUNCTIONALVIDPN
 - DXGKARG_RECOMMENDFUNCTIONALVIDPN
---

# _DXGKARG_RECOMMENDFUNCTIONALVIDPN structure


## -description

The DXGKARG_RECOMMENDFUNCTIONALVIDPN structure contains arguments for the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a> function. The <i>DxgkDdiRecommendFunctionalVidPn</i> function creates a functional video present network (VidPN) that can be implemented on a specified display adapter.

## -struct-fields

### -field NumberOfVidPnTargets

Reserved for future use.

### -field pVidPnTargetPrioritizationVector

Reserved for future use.

### -field hRecommendedFunctionalVidPn

A handle, provided by the caller, to an empty VidPN object. <i>DxgkDdiRecommendFunctionalVidPn</i> must add a path (source-target pair) to the VidPN's topology and must pin modes on the path's source and target. For information about adding paths to a topology and creating mode sets for video present sources and targets, see <a href="/windows-hardware/drivers/display/vidpn-objects-and-interfaces">VidPN Objects and Interfaces</a>.

### -field RequestReason

A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_recommendfunctionalvidpn_reason">DXGK_RECOMMENDFUNCTIONALVIDPN_REASON</a> value that indicates why the caller is requesting a functional VidPN.

### -field pPrivateDriverData

A pointer to a buffer that contains private data that is passed from a user-mode application to the display miniport driver.

### -field PrivateDriverDataSize

The size, in bytes, of the data block pointed to by <i>pPrivateDriverData</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>

