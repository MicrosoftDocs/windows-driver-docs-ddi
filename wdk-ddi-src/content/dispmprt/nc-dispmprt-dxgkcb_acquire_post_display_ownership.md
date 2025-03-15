---
UID: NC:dispmprt.DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
title: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP (dispmprt.h)
description: Learn more about the DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback function.
tech.root: display
ms.date: 01/06/2025
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
 - dispmprt/DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
---

# DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback function

## -description

A kernel-mode display miniport driver (KMD) calls *Dxgkrnl*'s **DxgkCbAcquirePostDisplayOwnership** routine to obtain the display information from the current power-on self-test (POST) display device or the previously running WDDM driver.

The driver must use this display information to optimize the initial mode change request after the display device has been started.

## -parameters

### -param DeviceHandle [in]

A handle that represents a display adapter. The KMD previously obtained this handle in the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md) structure that was passed to [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md).

### -param DisplayInfo [out]

Pointer to a [**DXGK_DISPLAY_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgk_display_information.md) structure that is allocated by the KMD. If **DxgkCbAcquirePostDisplayOwnership** returns STATUS_SUCCESS, this structure contains display information for the current display device that is used for POST operations.

## -returns

**DxgkCbAcquirePostDisplayOwnership** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

Calling **DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP** ensures that the driver correctly initializes the display settings based on the current or most recent display configuration, especially after system start-up, device plug-in events, or resuming from hibernation.

### Allowed color formats

The **DisplayInfo->ColorFormat** member must include a bitwise-OR combination of the following two [**D3DDDIFORMAT**](../d3dukmdt/ne-d3dukmdt-_d3dddiformat.md) formats:

* **D3DDDIFMT_X8R8G8B8**
* **D3DDDIFMT_A8R8G8B8**

If the OS reports back the **D3DDDIFMT_R8G8B8** format, the KMD should ignore it.

### Video present target initialization

It's possible that the **DisplayInfo->TargetId** member isn't initialized. In this case, the identifier of the video present target is **D3DDDI_ID_UNINITIALIZED**. Typically, this situation occurs after a system boot.

Similarly, it's possible that the **DisplayInfo->AcpiId** member isn't initialized. In this case, the ACPI identifier **AcpiId** has a value of zero.

In the case of a driver-to-driver upgrade, the previous driver will have provided the target identifier and the ACPI identifier.

### Implementation guidelines

Starting with WDDM 1.2, the KMD must follow these guidelines when it calls **DxgkCbAcquirePostDisplayOwnership**:

* The entry point for the **DxgkCbAcquirePostDisplayOwnership** function is part of the [**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md) structure. This structure is returned to the driver through the  **DxgkInterface** parameter when the driver's [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md) function is called.

* KMD can optionally call **DxgkCbAcquirePostDisplayOwnership**. However, the OS might still call KMD's[**DxgkDdiStopDeviceAndReleasePostDisplayOwnership**](nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md) function, even if the driver didn't previously call **DxgkCbAcquirePostDisplayOwnership**, and the driver must handle that call appropriately. If the driver's **DxgkDdiStopDeviceAndReleasePostDisplayOwnership** function doesn't complete successfully, the OS will call the driver's [**DxgkDdiStopDevice**](nc-dispmprt-dxgkddi_stop_device.md) function.

* The KMD can call **DxgkCbAcquirePostDisplayOwnership** if the device is started in response to a Plug and Play (PnP) event. In this case, the driver must call **DxgkCbAcquirePostDisplayOwnership** from within the context of the call to the [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md) function.

* The KMD can call **DxgkCbAcquirePostDisplayOwnership** if the device resumes a **PowerDeviceD0** power state after a hibernation state. In this case, the driver must call **DxgkCbAcquirePostDisplayOwnership** from within the context of the call to the [**DxgkDdiSetPowerState**](nc-dispmprt-dxgkddi_set_power_state.md) function.

* The KMD must only call the **DxgkCbAcquirePostDisplayOwnership** function if it's running at least Windows 8. The KMD can call [**RtlGetVersion**](../wdm/nf-wdm-rtlgetversion.md) to determine the version of the OS.

* **DxgkCbAcquirePostDisplayOwnership** can return a [**DXGK_DISPLAY_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgk_display_information.md) structure with the **Width** member set to zero. This value indicates that either the  current display device isn't capable of POST operations or the OS doesn't have the current display information for the current POST device.

## -see-also

[**D3DDDIFORMAT**](../d3dukmdt/ne-d3dukmdt-_d3dddiformat.md)

[**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md)

[**DXGK_DISPLAY_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgk_display_information.md)

[**DxgkDdiSetPowerState**](nc-dispmprt-dxgkddi_set_power_state.md)

[**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md)

[**DxgkDdiStopDeviceAndReleasePostDisplayOwnership**](nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md)

[**RtlGetVersion**](../wdm/nf-wdm-rtlgetversion.md)
