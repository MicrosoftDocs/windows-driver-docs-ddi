---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO (d3dkmddi.h)
description: The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_VIDPN_TARGET_MODE structure that the display miniport driver populates before calling pfnAddMode.
old-location: display\dxgk_vidpntargetmodeset_interface_pfncreatenewmodeinfo.htm
ms.assetid: ebb37681-fa03-49f5-968b-87c9ff4ebae9
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO callback function"]
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO, DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO callback, VidPnFunctions_96744b7d-68a5-4ea6-840b-eed33b627ec2.xml, d3dkmddi/pfnCreateNewModeInfo, display.dxgk_vidpntargetmodeset_interface_pfncreatenewmodeinfo, pfnCreateNewModeInfo, pfnCreateNewModeInfo callback function [Display Devices]
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
 - "d3dkmddi/pfnCreateNewModeInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnCreateNewModeInfo
product:
 - Windows
---

# DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO callback function

## -description

The <b>pfnCreateNewModeInfo</b> function returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure that the display miniport driver populates before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode">pfnAddMode</a>.

## -parameters

### -param hVidPnTargetModeSet

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param ppNewVidPnTargetModeInfo

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_TARGET_MODE structure allocated by the VidPN manager.

## -returns

The <b>pfnCreateNewModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|

## -remarks

The <b>pfnCreateNewModeInfo</b> function allocates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure and sets its <b>Id</b> member to a newly generated identifier.

After you call <b>pfnCreateNewModeInfo</b> to obtain a D3DKMDT_VIDPN_TARGET_MODE structure, you must do one, but not both, of the following:

<ul>
<li>
Populate the <b>Info</b> member of the structure and pass the structure to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode">pfnAddMode</a>.

</li>
<li>
Release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

</li>
</ul>
When you populate a D3DKMDT_VIDPN_TARGET_MODE structure, you have the option of overwriting the <b>Id</b> member that was generated and set by <b>pfnCreateNewModeInfo</b>. However, if you overwrite the <b>Id</b> member of any D3DKMDT_VIDPN_TARGET_MODE structure, you must overwrite the <b>Id</b> members of all the D3DKMDT_VIDPN_TARGET_MODE structures you obtain from <b>pfnCreateNewModeInfo</b>. Unless you have a specific reason for overwriting the <b>Id</b> members (for example, tracking target modes with your own numbering scheme), you should leave them as set by <b>pfnCreateNewModeInfo</b>.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode">pfnAddMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>

