---
UID: NC:dispmprt.DXGKDDI_ADD_DEVICE
title: DXGKDDI_ADD_DEVICE (dispmprt.h)
description: The DxgkDdiAddDevice function creates a context block for a display adapter and returns a handle that represents the display adapter.
old-location: display\dxgkddiadddevice.htm
tech.root: display
ms.date: 11/22/2021
keywords: ["DXGKDDI_ADD_DEVICE callback function"]
ms.keywords: DXGKDDI_ADD_DEVICE, DXGKDDI_ADD_DEVICE callback, DmFunctions_83323c62-42ac-45f5-80c8-b914fda642b5.xml, DxgkDdiAddDevice, DxgkDdiAddDevice callback function [Display Devices], display.dxgkddiadddevice, dispmprt/DxgkDdiAddDevice
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_ADD_DEVICE
 - dispmprt/DXGKDDI_ADD_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_ADD_DEVICE
---

# DXGKDDI_ADD_DEVICE callback function

## -description

The *DxgkDdiAddDevice* function creates a context block for a display adapter and returns a handle that represents the display adapter.

## -parameters

### -param PhysicalDeviceObject [in]

A pointer to a physical device object (PDO) that identifies a display adapter.

### -param MiniportDeviceContext [out]

A pointer to a variable that receives a handle, created by the display miniport driver, that will represent the display adapter identified by **PhysicalDeviceObject**. The display miniport driver can return NULL in this parameter to indicate that it will not support the display adapter identified by **PhysicalDeviceObject**.

## -returns

*DxgkDdiAddDevice* returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

The *DxgkDdiAddDevice* function allocates a private context block that is associated with the display adapter identified by **PhysicalDeviceObject**. You can think of the handle returned in **MiniportDeviceContext** as a handle to the display adapter or as a handle to the context block associated with the display adapter. The DirectX graphics kernel subsystem (*Dxgkrnl.sys*) will supply the handle in subsequent calls to the display miniport driver. The following list gives examples of various components of *Dxgkrnl.sys* passing the handle to functions implemented by the display miniport driver.

* The display port driver supplies the handle in the **MiniportDeviceContext** parameter of the [*DxgkDdiStartDevice*](nc-dispmprt-dxgkddi_start_device.md) function.

* The VidPN manager supplies the handle in the **hAdapter** parameter of the [*DxgkDdiIsSupportedVidPn*](../d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn.md) function.

* The DirectX graphics core supplies the handle in the **hAdapter** parameter of the [*DxgkDdiQueryAdapterInfo*](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

Do not be confused by the fact that sometimes the handle is named **MiniportDeviceContext** and sometimes it is named **hAdapter**. Also, do not confuse this handle with the **hDevice** parameter that is passed to certain display miniport driver functions.

*DxgkDdiAddDevice* is invoked for one device at a time in serial. Its behavior is the same as the standard [**DRIVER_ADD_DEVICE**](../wdm/nc-wdm-driver_add_device.md) callback for WDM kernel-mode drivers.

Some display adapter cards have two or more PCI functions that play the role of display adapter. For example, certain older cards implement multiple views by having a separate PCI function for each view. The display port driver calls *DxgkDdiAddDevice* once for each of those PCI functions, at which time the display miniport driver can indicate that it supports the PCI function (by setting **MiniportDeviceContext** to a nonzero value) or that it does not support the PCI function (by setting **MiniportDeviceContext** to NULL). To get information about a particular PCI function, the display miniport driver can pass **PhysicalDeviceObject** to [*IoGetDeviceProperty*](../wdm/nf-wdm-iogetdeviceproperty.md).

In [*DxgkDdiRemoveDevice*](nc-dispmprt-dxgkddi_remove_device.md), free your context block and any other resources you allocate during *DxgkDdiAddDevice*.

The *DxgkDdiAddDevice* function should be made pageable.

## -see-also

[*DxgkDdiRemoveDevice*](nc-dispmprt-dxgkddi_remove_device.md)

[*DxgkDdiStartDevice*](nc-dispmprt-dxgkddi_start_device.md)
