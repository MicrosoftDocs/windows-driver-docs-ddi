---
UID: NF:storport.StorPortHardwareReset
title: StorPortHardwareReset function
description: A miniport can call StorPortHardwareReset to issue a hardware reset.
tech.root: storage
ms.assetid: 99e1fcdc-a727-4198-b02e-f4906f7b3d69
ms.date: 03/24/2020
ms.topic: function
ms.keywords: StorPortHardwareReset
req.header: storport.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - StorPortHardwareReset
 - storport/StorPortHardwareReset
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortHardwareReset
product:
 - Windows
---

# StorPortHardwareReset function


## -description

A storage miniport can call **StorPortHardwareReset** to issue a hardware reset.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param Type

A [**STOR_DEVICE_RESET_TYPE**](ne-storport-stor_device_reset_type.md) enum that specifies the type of reset to be issued. Currently, *Type* must be set to **StorFunctionLevelReset**.

## -returns

**StorPortHardwareReset** returns a status code such as the following:

| Return code | Description |
|-------------|-------------|
| STOR_STATUS_INVALID_PARAMETER | *HwDeviceExtension* is invalid. |
| STOR_STATUS_NOT_IMPLEMENTED   | **Type** values other than **StorFunctionLevelReset** are not implemented. |
| STOR_STATUS_SUCCESS           | The hardware reset completed successfully. |
| STOR_STATUS_UNSUCCESSFUL      | The operation failed. |

## -remarks

See [Resetting and recovering a device](/windows-hardware/drivers/kernel/resetting-and-recovering-a-device
) for more details.

## -see-also

[**STOR_DEVICE_RESET_TYPE**](ne-storport-stor_device_reset_type.md)