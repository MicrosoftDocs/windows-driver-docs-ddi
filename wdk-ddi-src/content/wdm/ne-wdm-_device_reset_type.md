---
UID: NE:wdm._DEVICE_RESET_TYPE
title: _DEVICE_RESET_TYPE (wdm.h)
description: The DEVICE_RESET_TYPE enumeration specifies the type of device reset that is being requested by a call to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
old-location: kernel\device_reset_type.htm
tech.root: kernel
ms.assetid: 598044D9-8B99-453C-96FE-9B04C980BB3A
ms.date: 11/15/2018
ms.keywords: DEVICE_RESET_TYPE, DEVICE_RESET_TYPE enumeration [Kernel-Mode Driver Architecture], FunctionLevelDeviceReset, PlatformLevelDeviceReset, _DEVICE_RESET_TYPE, kernel.device_reset_type, wdm/DEVICE_RESET_TYPE, wdm/FunctionLevelDeviceReset, wdm/PlatformLevelDeviceReset
ms.topic: enum
f1_keywords:
 - "wdm/DEVICE_RESET_TYPE"
req.header: wdm.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- DEVICE_RESET_TYPE
product:
- Windows
targetos: Windows
req.typenames: DEVICE_RESET_TYPE
---

# _DEVICE_RESET_TYPE enumeration


## -description


The <b>DEVICE_RESET_TYPE</b> enumeration specifies the type of device reset that is being requested by a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a> routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. For more information see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](https://docs.microsoft.com/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard).


## -enum-fields


### -field FunctionLevelDeviceReset

A function-level device reset, which is restricted to a specific device.


### -field PlatformLevelDeviceReset

A platform-level device reset, which affects a specific device and all other devices that are connected to it via the same power rail or reset line.


## -see-also



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_reset_interface_standard">DEVICE_RESET_INTERFACE_STANDARD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a>


[Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](https://docs.microsoft.com/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard) 
 

 

