---
UID: NC:d3dkmddi.DXGKDDI_CREATEDEVICE
title: DXGKDDI_CREATEDEVICE (d3dkmddi.h)
description: Learn more about the DXGKDDI_CREATEDEVICE function.
old-location: display\dxgkddicreatedevice.htm
ms.date: 09/12/2022
keywords: ["DXGKDDI_CREATEDEVICE callback function"]
ms.keywords: DXGKDDI_CREATEDEVICE, DXGKDDI_CREATEDEVICE callback, DmFunctions_15d9141a-ec58-41f7-a925-768079604525.xml, DxgkDdiCreateDevice, DxgkDdiCreateDevice callback function [Display Devices], d3dkmddi/DxgkDdiCreateDevice, display.dxgkddicreatedevice
req.header: d3dkmddi.h
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
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_CREATEDEVICE
 - d3dkmddi/DXGKDDI_CREATEDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CREATEDEVICE
product:
 - Windows
---

# DXGKDDI_CREATEDEVICE callback function

## -description

The **DXGKDDI_CREATEDEVICE** function creates a graphics context device that is subsequently used in calls to the display miniport driver's device-specific functions.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCreateDevice

[in/out] Pointer to a [**DXGKARG_CREATEDEVICE**](ns-d3dkmddi-_dxgkarg_createdevice.md) structure that describes the graphics context device.

## -returns

**DXGKDDI_CREATEDEVICE** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | **DXGKDDI_CREATEDEVICE** successfully created the graphics context device.|
| STATUS_NO_MEMORY | **DXGKDDI_CREATEDEVICE** could not allocate memory that was required for it to complete.|

## -remarks

*Dxgkrnl* calls the display miniport driver's **DXGKDDI_CREATEDEVICE** function to create a graphics context device that the graphics subsystem subsequently passes in calls to the display miniport driver. The driver uses a device to hold a collection of rendering state. The graphics subsystem can create multiple devices in the same process on a given graphics processing unit (GPU) adapter.

> [!NOTE]
> The number of devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot have a hard-coded maximum device limit.

Generally, devices are independent of each other; in other words, resources that are created in one device cannot be referenced or accessed by resources that are created in another device. However, cross-process resources are an exception to this rule.

**DXGKDDI_CREATEDEVICE** should be made pageable.

## -see-also

[**DXGKARG_CREATEDEVICE**](ns-d3dkmddi-_dxgkarg_createdevice.md)

[**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)
