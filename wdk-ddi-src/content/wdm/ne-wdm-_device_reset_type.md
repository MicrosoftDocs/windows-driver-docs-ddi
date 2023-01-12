---
UID: NE:wdm._DEVICE_RESET_TYPE
title: _DEVICE_RESET_TYPE (wdm.h)
description: The DEVICE_RESET_TYPE enumeration specifies the type of device reset that is being requested by a call to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
tech.root: kernel
ms.date: 06/06/2022
keywords: ["DEVICE_RESET_TYPE enumeration"]
ms.keywords: DEVICE_RESET_TYPE, DEVICE_RESET_TYPE enumeration [Kernel-Mode Driver Architecture], FunctionLevelDeviceReset, PlatformLevelDeviceReset, _DEVICE_RESET_TYPE, kernel.device_reset_type, wdm/DEVICE_RESET_TYPE, wdm/FunctionLevelDeviceReset, wdm/PlatformLevelDeviceReset
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: DEVICE_RESET_TYPE
f1_keywords:
 - _DEVICE_RESET_TYPE
 - wdm/_DEVICE_RESET_TYPE
 - DEVICE_RESET_TYPE
 - wdm/DEVICE_RESET_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DEVICE_RESET_TYPE
 - DEVICE_RESET_TYPE
---

# _DEVICE_RESET_TYPE enumeration

## -description

The **DEVICE_RESET_TYPE** enumeration specifies the type of device reset that is being requested by a call to the [DeviceReset](./nc-wdm-device_reset_handler.md) routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.

For more information see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard).

## -enum-fields

### -field FunctionLevelDeviceReset

A function-level device reset, which is restricted to a specific device.

### -field PlatformLevelDeviceReset

A platform-level device reset, which affects a specific device and all other devices that are connected to it via the same power rail or reset line.

## -see-also

[DEVICE_RESET_INTERFACE_STANDARD](./ns-wdm-_device_reset_interface_standard.md)

[DeviceReset](./nc-wdm-device_reset_handler.md)

[Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard)