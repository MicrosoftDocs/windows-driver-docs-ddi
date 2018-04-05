---
UID: NC:d3dkmddi.DXGKDDI_DESTROYOVERLAY
title: DXGKDDI_DESTROYOVERLAY
author: windows-driver-content
description: The DxgkDdiDestroyOverlay function disables overlay hardware and deletes the specified overlay handle.
old-location: display\dxgkddidestroyoverlay.htm
old-project: display
ms.assetid: ea4672a2-ba21-42d4-9ff3-4fa611f86c90
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_DESTROYOVERLAY, DmFunctions_e4fa2e3e-ac60-4235-92cc-77e71116a4d4.xml, DxgkDdiDestroyOverlay, DxgkDdiDestroyOverlay callback function [Display Devices], d3dkmddi/DxgkDdiDestroyOverlay, display.dxgkddidestroyoverlay
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
-	DxgkDdiDestroyOverlay
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_DESTROYOVERLAY callback


## -description


The <i>DxgkDdiDestroyOverlay</i> function disables overlay hardware and deletes the specified overlay handle.


## -parameters




### -param hOverlay [in]

[in] A handle to the overlay to destroy. The display miniport driver's <a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a> structure. 


## -returns



<i>DxgkDdiDestroyOverlay</i> returns STATUS_SUCCESS, or an appropriate error result if overlay hardware is not successfully disabled.




## -remarks



<i>DxgkDdiDestroyOverlay</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a>



<a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a>
 

 

