---
UID: NC:d3dkmddi.DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH
title: DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH
author: windows-driver-content
description: The DxgkDdiUpdateActiveVidPnPresentPath function updates one of the video present paths that is currently active on the display adapter.
old-location: display\dxgkddiupdateactivevidpnpresentpath.htm
old-project: display
ms.assetid: 3bf5ebf7-8113-4ab2-beb1-1a52df25ac37
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH, DmFunctions_837597a1-a23e-4aa9-b219-b1f69eb58ed1.xml, DxgkDdiUpdateActiveVidPnPresentPath, DxgkDdiUpdateActiveVidPnPresentPath callback function [Display Devices], d3dkmddi/DxgkDdiUpdateActiveVidPnPresentPath, display.dxgkddiupdateactivevidpnpresentpath
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiUpdateActiveVidPnPresentPath
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH callback


## -description


The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function updates one of the video present paths that is currently active on the display adapter.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pUpdateActiveVidPnPresentPath








#### - pUpdateActiveVidPnPresentPathArg [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559494">DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH</a> structure, which contains one member: a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The members of the D3DKMDT_VIDPN_PRESENT_PATH structure identify the path and supply new settings for the path. The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function must program the path on the display adapter according to the new settings.


## -returns



<i>DxgkDdiUpdateActiveVidPnPresentPath</i>returns one of the following values:




## -remarks



The operating system calls the <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function to control the settings of video present paths, such as path rotation, a presented content's geometry transformations, gamma ramps that are used to adjust the presented content's brightness, and so on.

<div class="alert"><b>Note</b>    The display miniport driver's <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function must support gamma ramps.</div>
<div> </div>
Beginning with Windows 8, if the display miniport driver sets the <b>SupportSmoothRotation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a> structure, it must support updating the path rotation on the adapter using the <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function. The driver must always be able to set the path rotation during a call to the <a href="https://msdn.microsoft.com/979b86e9-f3ff-4022-8c00-b6afc2b1f747">DxgkDdiCommitVidPn</a> function.

The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559494">DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/979b86e9-f3ff-4022-8c00-b6afc2b1f747">DxgkDdiCommitVidPn</a>
 

 

