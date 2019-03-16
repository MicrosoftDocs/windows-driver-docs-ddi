---
UID: NC:d3dkmddi.DXGKDDI_UPDATEOVERLAY
title: DXGKDDI_UPDATEOVERLAY (d3dkmddi.h)
description: The DxgkDdiUpdateOverlay function modifies the overlay hardware.
old-location: display\dxgkddiupdateoverlay.htm
ms.assetid: b131dbb9-1e11-4d04-97cb-e15ec2b025c7
ms.date: 05/10/2018
ms.keywords: DXGKDDI_UPDATEOVERLAY, DXGKDDI_UPDATEOVERLAY callback, DmFunctions_cc73fb5c-c4b9-476a-9227-fe2d15e288ea.xml, DxgkDdiUpdateOverlay, DxgkDdiUpdateOverlay callback function [Display Devices], d3dkmddi/DxgkDdiUpdateOverlay, display.dxgkddiupdateoverlay
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
- DxgkDdiUpdateOverlay
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_UPDATEOVERLAY callback function


## -description


The <i>DxgkDdiUpdateOverlay</i> function modifies the overlay hardware.


## -parameters




### -param hOverlay [in]

[in] A handle to the overlay to modify. The display miniport driver's <a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a> structure that <i>pCreateOverlay</i> points to. 


### -param pUpdateOverlay [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559496">DXGKARG_UPDATEOVERLAY</a> structure that describes how to modify the overlay hardware.


## -returns



<i>DxgkDdiUpdateOverlay</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiUpdateOverlay successfully modified the overlay.|
|STATUS_INVALID_PARAMETER|Parameters that were passed to DxgkDdiUpdateOverlay contained errors that prevented it from completing.|
|STATUS_NO_MEMORY|DxgkDdiUpdateOverlay could not allocate memory that was required for it to complete.|
|STATUS_INSUFFICIENT_RESOURCES|DxgkDdiUpdateOverlay could not complete because insufficient bandwidth was available or the requested overlay hardware could not complete the task.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiUpdateOverlay.|




## -remarks



<i>DxgkDdiUpdateOverlay</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559496">DXGKARG_UPDATEOVERLAY</a>



<a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a>
 

 

