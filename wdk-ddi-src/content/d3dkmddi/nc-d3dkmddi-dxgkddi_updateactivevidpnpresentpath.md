---
UID: NC:d3dkmddi.DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH
title: DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH (d3dkmddi.h)
description: The DxgkDdiUpdateActiveVidPnPresentPath function updates one of the video present paths that is currently active on the display adapter.
old-location: display\dxgkddiupdateactivevidpnpresentpath.htm
ms.assetid: 3bf5ebf7-8113-4ab2-beb1-1a52df25ac37
ms.date: 05/10/2018
ms.keywords: DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH, DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH callback, DmFunctions_837597a1-a23e-4aa9-b219-b1f69eb58ed1.xml, DxgkDdiUpdateActiveVidPnPresentPath, DxgkDdiUpdateActiveVidPnPresentPath callback function [Display Devices], d3dkmddi/DxgkDdiUpdateActiveVidPnPresentPath, display.dxgkddiupdateactivevidpnpresentpath
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DxgkDdiUpdateActiveVidPnPresentPath"
req.header: d3dkmddi.h
req.include-header: 
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
- DxgkDdiUpdateActiveVidPnPresentPath
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH callback function


## -description


The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function updates one of the video present paths that is currently active on the display adapter.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -param pUpdateActiveVidPnPresentPath

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_updateactivevidpnpresentpath">DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH</a> structure, which contains one member: a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The members of the D3DKMDT_VIDPN_PRESENT_PATH structure identify the path and supply new settings for the path. The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function must program the path on the display adapter according to the new settings.


## -returns



<i>DxgkDdiUpdateActiveVidPnPresentPath</i>returns one of the following values:

| Value | Description |
| --- | --- |
|STATUS_SUCCESS | The function succeeded.|
|STATUS_GRAPHICS_PATH_NOT_IN_TOPOLOGY|The path specified by *pUpdateActiveVidPnPresentPathArg*->**VidPnPresentPathInfo** is not in the topology of the active VidPN.|
|STATUS_GRAPHICS_PATH_CONTENT_GEOMETRY_TRANSFORMATION_NOT_SUPPORTED|The path does not support the content transformation specified by *pUpdateActiveVidPnPresentPathArg*->**VidPnPresentPathInfo.ContentTransformation**. The path does not support the gamma ramp specified by *pUpdateActiveVidPnPresentPathArg*->**VidPnPresentPathInfo.GammaRamp**.|


## -remarks



The operating system calls the <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function to control the settings of video present paths, such as path rotation, a presented content's geometry transformations, gamma ramps that are used to adjust the presented content's brightness, and so on.

<div class="alert"><b>Note</b>    The display miniport driver's <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function must support gamma ramps.</div>
<div> </div>
Beginning with Windows 8, if the display miniport driver sets the <b>SupportSmoothRotation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure, it must support updating the path rotation on the adapter using the <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function. The driver must always be able to set the path rotation during a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function.

The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_updateactivevidpnpresentpath">DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>
 

 

