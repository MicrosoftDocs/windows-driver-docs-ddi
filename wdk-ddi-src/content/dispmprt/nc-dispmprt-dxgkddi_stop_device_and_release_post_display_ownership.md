---
UID: NC:dispmprt.DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
title: DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP (dispmprt.h)
description: Learn more about the DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback function.
tech.root: display
ms.date: 01/06/2025
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
 - dispmprt/DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
---

# DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback function

## -description

The OS calls the kernel-mode display driver's (KMD) **DxgkddiStopDeviceAndReleasePostDisplayOwnership** function to request that KMD reset the display device and release ownership of the current power-on self-test (POST) device.

## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to the DirectX graphics kernel subsystem (*Dxgkrnl*).

### -param TargetId [in]

A **D3DDDI_VIDEO_PRESENT_TARGET_ID** value that specifies the identifier of the video present target on the display adapter that the display device is connected to. This identifier could be for the target that was left in the current video present network (VidPN) state during the previous call to [**DxgkDdiCommitVidPn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn.md).

For more details about the use of the **TargetId** parameter, see the Remarks section.

### -param DisplayInfo [out]

A pointer to a [**DXGK_DISPLAY_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgk_display_information.md) structure that is allocated by the OS.

## -returns

Returns **STATUS_SUCCESS** if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*. For more information, see the Remarks section.

## -remarks

Starting with Windows 8 (WDDM 1.2), the OS calls this function during a Plug and Play (PnP) stop operation.

To indicate to the OS that this function is supported, the driver must set the **NonVGASupport** member of the [**DXGK_DRIVERCAPS**](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md) structure when its [**DxgkDdiQueryAdapterInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function is called.

### Allowed color formats

The KMD should report only a 32-bit color format. Therefore the **DisplayInfo->ColorFormat** member must include only one of the following two [**D3DDDIFORMAT**](../d3dukmdt/ne-d3dukmdt-_d3dddiformat.md) formats:

* **D3DDDIFMT_X8R8G8B8**
* **D3DDDIFMT_A8R8G8B8**

### Video present target initialization

The KMD must set the **DisplayInfo->TargetId** member to the target identifier of the display that remains active. Typically, this identifier will be the value of the **TargetId** parameter that the OS passed to the driver.

Similarly, the KMD must set the **DisplayInfo->AcpiId** member to the ACPI identifier of the display that remains active.

### Required steps by the KMD

The KMD must follow these steps when its **DxgkDdiStopDeviceAndReleasePostDisplayOwnership** function is called:

1. Stop the display device associated with the video present target indicated by the **TargetId** parameter but must keep the display associated with this target powered on and visible.

1. Check the connectivity of the display associated with this target. If the target doesn't have a display connected, the KMD must complete the call to this function and return the **STATUS_NOT_SUPPORTED** error code.

1. Disable the signal to all other displays that are connected to the display adapter. If this is not possible, the driver should attempt to place a blank image on all other displays. If this is not possible, the driver must leave the last image on the screen unchanged.

1. Keep the current display mode on the indicated target and provide this mode back to the OS as part of this function call.

1. If the driver can't maintain the current display mode, or if the target isn't part of the active topology, the driver should select an alternate active target and attempt to maintain the current resolution of that target. If that isn't possible, the driver should attempt to set the display to its native resolution or to a high-resolution mode. In this case, the display resolution must be set to at least 800 x 600 pixels in either **D3DDDIFMT_R8G8B8** (24 bits per pixel) or **D3DDDIFMT_X8R8G8B8** (32 bpp) color formats.

1. If no target is active, the driver should attempt to enable a target, preferably the internal panel, if it is available.

1. If possible, the driver must clear the current frame buffer and disable the hardware cursor and all display overlays.

1. If possible, the driver must set the gamma ramp of the device to its default values.

1. The driver must set the current frame buffer to be in a linear mode. The driver does this either by using the default swizzle range or by disabling swizzle mode.

1. The driver must make the current frame buffer accessible to the CPU by mapping the  current frame buffer linearly into the CPU address space.

1. The driver must ensure that the visibility of the indicated target is set to "enabled."

After the KMD performs these steps, it must return the current display settings for the device. The driver returns this information by setting the members of the [**DXGK_DISPLAY_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgk_display_information.md) structure that is referenced by the **DisplayInfo** parameter.

After the device has been stopped, this display information might be used by the Windows generic display driver to manage the display device.

### Other requirements

On systems that support the Unified Extensible Firmware Interface (UEFI), a VGA basic input/output system (BIOS) doesn't exist. To support PnP stop operations on these systems, WDDM 1.2 and later provides support for the OS to reset the POST device and to get its display information during a PnP stop operation.  The OS does this by calling the KMD's **DxgkDdiStopDeviceAndReleasePostDisplayOwnership** function.

A PnP stop operation can occur in response to requests by processes such as the Device Manager, or during a driver upgrade process.

Starting with Windows 8, the OS calls the driver's **DxgkDdiStopDeviceAndReleasePostDisplayOwnership** function only on the POST device during a PnP stop operation.

It's optional for KMD to call [**DxgkCbAcquirePostDisplayOwnership**](nc-dispmprt-dxgkcb_acquire_post_display_ownership.md). However, the OS might still call KMD's **DxgkDdiStopDeviceAndReleasePostDisplayOwnership** function regardless of whether the driver made a previous call to **DxgkCbAcquirePostDisplayOwnership**.

If the driver successfully completes a call to this function, the OS won't call KMD's [**DxgkDdiStopDevice**](nc-dispmprt-dxgkddi_stop_device.md) function. If the driver fails to complete a call to this function, the OS will call **DxgkDdiStopDevice**, and device behavior will be the same as in Windows 7.

On UEFI-only systems, if the KMD fails a call to this function, a black screen is displayed and the IHV driver isn't installed. The workaround to this scenario is for the user to reboot the computer.

For more information on how this function is used in PnP scenarios, see [Plug and Play (PnP) in WDDM 1.2 and later](/windows-hardware/drivers/display/plug-and-play--pnp--start-and-stop-cases).

## -see-also

[**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md)

[**DXGK_DISPLAY_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgk_display_information.md)

[**DXGK_DRIVERCAPS**](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md)

[**DxgkCbAcquirePostDisplayOwnership**](nc-dispmprt-dxgkcb_acquire_post_display_ownership.md)

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiQueryAdapterInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md)

[**DxgkDdiStopDevice**](nc-dispmprt-dxgkddi_stop_device.md)
