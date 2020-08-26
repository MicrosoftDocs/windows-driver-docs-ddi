---
UID: NC:dispmprt.DXGKDDI_NOTIFY_SURPRISE_REMOVAL
title: DXGKDDI_NOTIFY_SURPRISE_REMOVAL (dispmprt.h)
description: Called by the operating system after a user disconnected an external display device without notifying the system.Can optionally be implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.
old-location: display\dxgkddinotifysurpriseremoval.htm
tech.root: display
ms.assetid: 4e6403e7-7463-479a-8be9-4136287b375e
ms.date: 08/05/2020
keywords: ["DXGKDDI_NOTIFY_SURPRISE_REMOVAL callback function"]
ms.keywords: DXGKDDI_NOTIFY_SURPRISE_REMOVAL, DXGKDDI_NOTIFY_SURPRISE_REMOVAL callback, DxgkDdiNotifySurpriseRemoval, DxgkDdiNotifySurpriseRemoval callback function [Display Devices], display.dxgkddinotifysurpriseremoval, dispmprt/DxgkDdiNotifySurpriseRemoval
f1_keywords:
 - "dispmprt/DxgkDdiNotifySurpriseRemoval"
 - "DxgkDdiNotifySurpriseRemoval"
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
targetos: Windows
req.typenames: 
---

# DXGKDDI_NOTIFY_SURPRISE_REMOVAL callback function

## -description

**DXGKDDI_NOTIFY_SURPRISE_REMOVAL** is called by the operating system when a user disconnects an external display device without notifying the system.

## -parameters

### -param MiniportDeviceContext 
[in]
A handle to a context block associated with a display adapter. The display miniport driver's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to the DirectX graphics kernel subsystem.

### -param RemovalType 
[in]
A value of type [**DXGK_SURPRISE_REMOVAL_TYPE**](ne-dispmprt-_dxgk_surprise_removal_type.md) that identifies the type of surprise removal event.

## -returns

Returns **STATUS_SUCCESS** if software resources were cleaned up for **RemovalType** = **DxgkRemovalHibernation**. If the driver instead returns an error code, the operating system will attempt to reboot the system, as described in the following Remarks section.

## -remarks

This callback can be optionally be implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.

> [!NOTE]
>
> The operating system calls **DxgkDdiNotifySurpriseRemoval** only if the display miniport driver indicates support by setting the **SupportSurpriseRemovalInHibernation** member of the [**DXGK_DRIVERCAPS**](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md) structure to 1.

When the OS detects a surprise removal, it notifies the driver as quickly as possible. **DxgkDdiNotifySurpriseRemoval** is a [level zero](https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level) DDI function, which means that it can be called when a driver has pending GPU workload and/or is running inside other DDI functions. Since a call to this function indicates the graphics hardware has been physically removed or has disappeared from system, any further attempt to access hardware might cause problems such as a hard hang.

The OS categorizes surprise removal as follows:

* The surprise removal occurs when the system and graphics device are in a low-power state, such as sleep or hibernation. When the OS resumes from the low power state, it detects this surprise removal and immediately calls the driver's **DxgkDdiNotifySurpriseRemoval** callback with **RemovalType = DxgkRemovalHibernation**. There will not likely any pending GPU work or DDI calls in this case, so it should be relatively safe and easy for the driver to handle. Return status details are as follows:

  * The OS expects the driver to handle the **DxgkDdiNotifySurpriseRemoval** call correctly and return **STATUS_SUCCESS**.
  * If the removed graphics device is the power-on self-test (POST) device, the OS will try to reboot the system gracefully regardless of the returned status.
  * For a non-POST device, if the driver fails the call and only supports **SupportSurpriseRemovalInHibernation** in its [**DXGK_DRIVERCAPS**](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md), the OS will reboot the system gracefully. If it supports **SupportSurpriseRemoval** in **DXGK_DRIVERCAPS**, the OS will ignore the return status and continue stopping the graphics device. See additional return notes below.

* The graphics device is surprise removed/unplugged when it is still running. When the OS detects this type of surprise removal, it immediately calls the driver's **DxgkDdiNotifySurpriseRemoval** callback with **RemovalType = DxgkRemovalPnPNotify**. There might still be some pending GPU work or DDI calls to complete in this case. When the driver receives this notification and can handle this surprise removal, the driver should immediately mark this device as surprise removal in its own device context to avoid any hardware access and then return STATUS_SUCCESS back to the OS. The OS will continue calling other DDI functions to clean up the resources and stop the graphics device. As noted below, the driver should only release or clean up the software resources and must not touch or access any hardware in these DDI calls. If the driver cannot handle this surprise removal, it should return a proper failure to the OS. For any failure, the OS will bugcheck the system immediately to avoid any further hardware or data damage.

If the display miniport driver returns **STATUS_SUCCESS**, the DirectX graphics kernel subsystem will continue to remove the external display adapter from the graphics stack and will call other driver-implemented *DxgkDdiXxx* kernel-mode functions to release all resources. In this case, the driver must complete its cleanup of software resources in response to calls from the operating system but must not touch or clean any hardware settings. If no other hardware is using the driver, the operating system will unload the driver.

If the driver returns an error code, does not set [**DXGK_DRIVERCAPS**](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md).**SupportSurpriseRemovalInHibernation**, or does not implement this function, the DirectX graphics kernel subsystem will not call any more driver-implemented *DxgkDdiXxx* functions and will attempt to reboot the system. In this case, the resource that was allocated before the external display device was disconnected will not be released.

## -see-also

[**D3DKMT_WDDM_1_2_CAPS**](https://docs.microsoft.com/windows-hardware/drivers/display/d3dkmt-wddm-1-2-caps)

[**DXGK_DRIVERCAPS**](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md)

[**DXGK_SURPRISE_REMOVAL_TYPE**](ne-dispmprt-_dxgk_surprise_removal_type.md)

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)
