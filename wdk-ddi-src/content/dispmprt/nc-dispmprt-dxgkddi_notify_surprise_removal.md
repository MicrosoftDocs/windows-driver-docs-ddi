---
UID: NC:dispmprt.DXGKDDI_NOTIFY_SURPRISE_REMOVAL
title: DXGKDDI_NOTIFY_SURPRISE_REMOVAL (dispmprt.h)
description: Called by the operating system after a user disconnected an external display device without notifying the system.Can optionally be implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.
old-location: display\dxgkddinotifysurpriseremoval.htm
tech.root: display
ms.assetid: 4e6403e7-7463-479a-8be9-4136287b375e
ms.date: 05/10/2018
ms.keywords: DXGKDDI_NOTIFY_SURPRISE_REMOVAL, DXGKDDI_NOTIFY_SURPRISE_REMOVAL callback, DxgkDdiNotifySurpriseRemoval, DxgkDdiNotifySurpriseRemoval callback function [Display Devices], display.dxgkddinotifysurpriseremoval, dispmprt/DxgkDdiNotifySurpriseRemoval
f1_keywords:
 - "dispmprt/DxgkDdiNotifySurpriseRemoval"
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- Dispmprt.h
api_name:
- DxgkDdiNotifySurpriseRemoval
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_NOTIFY_SURPRISE_REMOVAL callback function


## -description


Called by the operating system after a user disconnected an external display device without notifying the system.Can optionally be implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.




## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param RemovalType [in]

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ne-dispmprt-_dxgk_surprise_removal_type">DXGK_SURPRISE_REMOVAL_TYPE</a> that identifies the type of surprise removal event.


## -returns




      Returns <b>STATUS_SUCCESS</b> if software resources were cleaned up for <i>RemovalType</i> = <b>DxgkRemovalHibernation</b>. If the driver instead returns an error code, the operating system will attempt to reboot the system, as described in the following Remarks section.




## -remarks



The operating system calls <i>DxgkDdiNotifySurpriseRemoval</i> only if the display miniport driver indicates support by setting the <b>SupportSurpriseRemovalInHibernation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure to 1.

<div class="alert"><b>Note</b>  This function is called only if the disconnected external display device was in hibernation mode. This is indicated by <i>RemovalType</i> = <b>DxgkRemovalHibernation</b>, the only available value.</div>
<div> </div>
If the display miniport driver returns <b>STATUS_SUCCESS</b>, the DirectX graphics kernel subsystem will continue to remove the  external display adapter from the graphics stack and will call other driver-implemented <i>DxgkDdiXxx</i> kernel-mode functions to release all resources. In this case, the driver must complete its cleanup of software resources in response to calls from the operating system but must not touch or clean any hardware settings. If no other hardware is using the driver, the operating system will unload the driver.

If the driver returns an error code, does not set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>.<b>SupportSurpriseRemovalInHibernation</b>, or does not implement this function, the DirectX graphics kernel subsystem  will not call any more driver-implemented <i>DxgkDdiXxx</i> functions and will attempt to reboot the system. In this case, the resource that was allocated before the external display device was disconnected will not be released.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/d3dkmt-wddm-1-2-caps">D3DKMT_WDDM_1_2_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ne-dispmprt-_dxgk_surprise_removal_type">DXGK_SURPRISE_REMOVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

