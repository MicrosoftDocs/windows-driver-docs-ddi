---
UID: NC:d3dkmddi.DXGKDDI_CLOSEALLOCATION
title: DXGKDDI_CLOSEALLOCATION
author: windows-driver-content
description: The DxgkDdiCloseAllocation function unbinds device-specific allocations that the DxgkDdiOpenAllocation function created.
old-location: display\dxgkddicloseallocation.htm
old-project: display
ms.assetid: f9c195d7-debe-495e-a355-e176d06884f8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_CLOSEALLOCATION, DmFunctions_357920c4-694d-48f8-97ef-aa367e210a59.xml, DxgkDdiCloseAllocation, DxgkDdiCloseAllocation callback function [Display Devices], d3dkmddi/DxgkDdiCloseAllocation, display.dxgkddicloseallocation
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
-	DxgkDdiCloseAllocation
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CLOSEALLOCATION callback


## -description


The <i>DxgkDdiCloseAllocation</i> function unbinds device-specific allocations that the <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function created.


## -parameters




### -param hDevice [in]

[in] A handle to the graphics context device that allocations are unbound from. The display miniport driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a> structure. 


### -param pCloseAllocation [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557543">DXGKARG_CLOSEALLOCATION</a> structure that contains information about unbinding allocations.


## -returns



<i>DxgkDdiCloseAllocation</i> returns STATUS_SUCCESS, or an appropriate error result if the allocations are not successfully unbound from the graphics context device. 




## -remarks



Before the display miniport driver receives a call to its <a href="https://msdn.microsoft.com/cade544a-f9c6-4635-ab57-d09d694ca315">DxgkDdiDestroyAllocation</a> function to release allocations, the driver calls the <i>DxgkDdiCloseAllocation</i> function to close all bindings to those allocations. 

For a resource that contains multiple allocations, the DirectX graphics kernel subsystem directs <i>DxgkDdiCloseAllocation</i> to simultaneously close all of the allocations by specifying the handles to the device-specific allocations in the <b>pOpenHandleList</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557543">DXGKARG_CLOSEALLOCATION</a> structure. 

<i>DxgkDdiCloseAllocation</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557543">DXGKARG_CLOSEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>



<a href="https://msdn.microsoft.com/cade544a-f9c6-4635-ab57-d09d694ca315">DxgkDdiDestroyAllocation</a>



<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>
 

 

