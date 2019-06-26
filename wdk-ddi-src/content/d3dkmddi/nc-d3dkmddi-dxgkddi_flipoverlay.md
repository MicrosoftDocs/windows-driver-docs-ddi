---
UID: NC:d3dkmddi.DXGKDDI_FLIPOVERLAY
title: DXGKDDI_FLIPOVERLAY (d3dkmddi.h)
description: The DxgkDdiFlipOverlay function displays a new allocation by using the specified overlay.
old-location: display\dxgkddiflipoverlay.htm
ms.assetid: 9e35a48b-1741-4ee2-8e15-6ce51ad4c0ad
ms.date: 05/10/2018
ms.keywords: DXGKDDI_FLIPOVERLAY, DXGKDDI_FLIPOVERLAY callback, DmFunctions_fac1657b-03ec-4d63-93d6-3458423a1fe9.xml, DxgkDdiFlipOverlay, DxgkDdiFlipOverlay callback function [Display Devices], d3dkmddi/DxgkDdiFlipOverlay, display.dxgkddiflipoverlay
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkDdiFlipOverlay
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_FLIPOVERLAY callback function


## -description


The <i>DxgkDdiFlipOverlay</i> function displays a new allocation by using the specified overlay.


## -parameters




### -param hOverlay [in]

[in] A handle to the overlay to be flipped. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a> structure. 


### -param pFlipOverlay [in]

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_flipoverlay">DXGKARG_FLIPOVERLAY</a> structure that describes the new allocation to display by using the overlay.


## -returns



<i>DxgkDdiFlipOverlay</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiFlipOverlay successfully displays the new allocation.|
|STATUS_INVALID_PARAMETER|Parameters that were passed to DxgkDdiFlipOverlay contained errors that prevented it from completing.|
|STATUS_NO_MEMORY|DxgkDdiFlipOverlay could not allocate memory that was required for it to complete.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiFlipOverlay.|


## -remarks



<i>DxgkDdiFlipOverlay</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_flipoverlay">DXGKARG_FLIPOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay">DxgkDdiCreateOverlay</a>
 

 

