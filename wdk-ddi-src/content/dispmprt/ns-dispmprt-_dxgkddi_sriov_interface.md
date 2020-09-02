---
UID: NS:dispmprt._DXGKDDI_SRIOV_INTERFACE
title: _DXGKDDI_SRIOV_INTERFACE
author: windows-driver-content
description: The SRIOV device interface exposes the PCIe virtual devices.
tech.root: display
ms.assetid: 2b5a7fed-5c3d-4831-8274-14f9f70e3fe3
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_SRIOV_INTERFACE structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKDDI_SRIOV_INTERFACE, DXGKDDI_SRIOV_INTERFACE, *PDXGKDDI_SRIOV_INTERFACE,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKDDI_SRIOV_INTERFACE, *PDXGKDDI_SRIOV_INTERFACE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKDDI_SRIOV_INTERFACE
 - dispmprt/_DXGKDDI_SRIOV_INTERFACE
 - PDXGKDDI_SRIOV_INTERFACE
 - dispmprt/PDXGKDDI_SRIOV_INTERFACE
 - DXGKDDI_SRIOV_INTERFACE
 - dispmprt/DXGKDDI_SRIOV_INTERFACE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKDDI_SRIOV_INTERFACE
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKDDI_SRIOV_INTERFACE structure


## -description

The SRIOV device interface exposes the PCIe virtual devices.  

Functions to interact with the virtual device’s (GPU partitions) configuration space are exposed along with how the device will appear in the guest (BARs, vendor ID etc.). Finally, power state control functions are exposed to enable/disable/reset VFs. This interface is exposed even for devices that do not directly support SR-IOV in hardware. In the case of no hardware SR-IOV support, the virtual functions are managed by the kernel mode driver itself and are in effect virtualized themselves.

A miniport driver must support all functions in this group.

## -struct-fields

### -field Size

Size.

### -field Version

Version.

### -field Context

The context.

### -field InterfaceReference

Reference.

### -field InterfaceDereference

Deference.

### -field DxgkDdiReadVirtualFunctionConfig

[DxgkDdiReadVirtualFunctionConfig](nc-dispmprt-dxgkddi_readvirtualfunctionconfig.md)

### -field DxgkDdiWriteVirtualFunctionConfig

[DxgkDdiWriteVirtualFunctionConfig](nc-dispmprt-dxgkddi_writevirtualfunctionconfig.md)

### -field DxgkDdiReadVirtualFunctionConfigBlock

[DxgkDdiReadVirtualFunctionConfigBlock](nc-dispmprt-dxgkddi_readvirtualfunctionconfigblock.md)

### -field DxgkDdiWriteVirtualFunctionConfigBlock

[DxgkDdiWriteVirtualFunctionConfigBlock](nc-dispmprt-dxgkddi_writevirtualfunctionconfigblock.md)

### -field DxgkDdiQueryProbedBars

[DxgkDdiQueryProbedBars](nc-dispmprt-dxgkddi_queryprobedbars.md)

### -field DxgkDdiGetVendorAndDevice

[DxgkDdiGetVendorAndDevice](nc-dispmprt-dxgkddi_getvendoranddevice.md)

### -field DxgkDdiGetDeviceLocation

[DxgkDdiGetDeviceLocation](nc-dispmprt-dxgkddi_getdevicelocation.md)

### -field DxgkDdiResetVirtualFunction

[DxgkDdiResetVirtualFunction](nc-dispmprt-dxgkddi_resetvirtualfunction.md)

### -field DxgkDdiSetVirtualFunctionPowerState

[DxgkDdiSetVirtualFunctionPowerState](nc-dispmprt-dxgkddi_setvirtualfunctionpowerstate.md)

### -field DxgkDdiGetResourceForBar

[DxgkDdiGetResourceForBar](nc-dispmprt-dxgkddi_getresourceforbar.md)

### -field DxgkDdiQueryVirtualFunctionLuid

 
[DxgkDdiQueryVirtualFunctionLuid](nc-dispmprt-dxgkddi_queryvirtualfunctionluid.md)

## -remarks

## -see-also

