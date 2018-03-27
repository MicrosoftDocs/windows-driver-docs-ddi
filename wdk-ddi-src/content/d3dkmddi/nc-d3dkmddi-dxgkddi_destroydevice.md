---
UID: NC:d3dkmddi.DXGKDDI_DESTROYDEVICE
title: DXGKDDI_DESTROYDEVICE
author: windows-driver-content
description: The DxgkDdiDestroyDevice function destroys a graphics context device.
old-location: display\dxgkddidestroydevice.htm
old-project: display
ms.assetid: c067fe92-2364-4122-a7ed-03df7906ae64
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_DESTROYDEVICE, DmFunctions_14927367-d2f9-4aa4-ab3d-a3c8decedbcf.xml, DxgkDdiDestroyDevice, DxgkDdiDestroyDevice callback function [Display Devices], d3dkmddi/DxgkDdiDestroyDevice, display.dxgkddidestroydevice
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
-	DxgkDdiDestroyDevice
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_DESTROYDEVICE callback


## -description


The <i>DxgkDdiDestroyDevice</i> function destroys a graphics context device.


## -parameters




### -param hDevice [in]

[in] A handle to the graphics context device that <i>DxgkDdiDestroyDevice</i> will destroy. The display miniport driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a> structure. 


## -returns



<i>DxgkDdiDestroyDevice</i> returns STATUS_SUCCESS, or an appropriate error result if the graphics context device is not successfully destroyed. 




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiDestroyDevice</i> function to destroy a graphics context device that the driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function created. <i>DxgkDdiDestroyDevice</i> should free all of the resources that were allocated for the device and clean up any internal tracking data structures. 

<i>DxgkDdiDestroyDevice</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DESTROYDEVICE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

