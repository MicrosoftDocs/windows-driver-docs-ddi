---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_CREATENEWTARGETMODESET
title: DXGKDDI_VIDPN_CREATENEWTARGETMODESET (d3dkmddi.h)
description: The pfnCreateNewTargetModeSet function creates a new target mode set object within a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfncreatenewtargetmodeset.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPN_CREATENEWTARGETMODESET callback function"]
ms.keywords: DXGKDDI_VIDPN_CREATENEWTARGETMODESET, DXGKDDI_VIDPN_CREATENEWTARGETMODESET callback, VidPnFunctions_5bdc542e-e774-434b-a634-84ca5ed07d8d.xml, d3dkmddi/pfnCreateNewTargetModeSet, display.dxgk_vidpn_interface_pfncreatenewtargetmodeset, pfnCreateNewTargetModeSet, pfnCreateNewTargetModeSet callback function [Display Devices]
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
 - DXGKDDI_VIDPN_CREATENEWTARGETMODESET
 - d3dkmddi/DXGKDDI_VIDPN_CREATENEWTARGETMODESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VIDPN_CREATENEWTARGETMODESET
product:
 - Windows
---

# DXGKDDI_VIDPN_CREATENEWTARGETMODESET callback function


## -description

The <b>pfnCreateNewTargetModeSet</b> function creates a new target mode set object within a specified VidPN object.

## -parameters

### -param hVidPn

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, or <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.

### -param VidPnTargetId

[in] An integer that identifies one of the video present targets associated with the VidPN object.

### -param phNewVidPnTargetModeSet

[out] A pointer to a variable that receives a handle to the newly created target mode set object.

### -param ppVidPnTargetModeSetInterace

[out] A pointer to a variable that receives a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface">DXGK_VIDPNTARGETMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the target mode set object.

## -returns

The <b>pfnCreateNewTargetModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_NO_MEMORY|The VidPN manager was unable to allocate the memory required to create the new target mode set object.|

## -remarks

To assign a new target mode set to a particular target in a VidPN implementation, perform the following steps:

<ol>
<li>
Call <b>pfnCreateNewTargetModeSet</b> to get a handle to a new target mode set object. That target mode set object belongs to a particular VidPN object that you specify.

</li>
<li>
Use the functions of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface">DXGK_VIDPNTARGETMODESET_INTERFACE</a> structure to add modes to the target mode set object.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset">pfnAssignTargetModeSet</a> to assign the new target mode set to a particular target.

</li>
</ol>
If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then pass that handle to <b>pfnAssignTargetModeSet</b>, you do not need to release  the handle by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then you decide not to assign the new target mode set to a target, you must release the newly obtained handle by calling <b>pfnReleaseTargetModeSet</b>.

The lifetime of the DXGK_VIDPNTARGETEMODESET_INTERFACE structure returned in <i>ppVidPnTargetModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">VidPN Target Mode Set Interface</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset">pfnAssignTargetModeSet</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a>

