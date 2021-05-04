---
UID: NS:storport._STOR_RICH_DEVICE_DESCRIPTION
tech.root: storage
title: STOR_RICH_DEVICE_DESCRIPTION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_RICH_DEVICE_DESCRIPTION is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitRichDescription.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_RICH_DEVICE_DESCRIPTION, *PSTOR_RICH_DEVICE_DESCRIPTION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_RICH_DEVICE_DESCRIPTION
 - PSTOR_RICH_DEVICE_DESCRIPTION
 - STOR_RICH_DEVICE_DESCRIPTION
f1_keywords:
 - _STOR_RICH_DEVICE_DESCRIPTION
 - storport/_STOR_RICH_DEVICE_DESCRIPTION
 - PSTOR_RICH_DEVICE_DESCRIPTION
 - storport/PSTOR_RICH_DEVICE_DESCRIPTION
 - STOR_RICH_DEVICE_DESCRIPTION
 - storport/STOR_RICH_DEVICE_DESCRIPTION
dev_langs:
 - c++
---

## -description

**STOR_RICH_DEVICE_DESCRIPTION** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitRichDescription**.

## -struct-fields

### -field Version

The version of the structure. This value should be **STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION_V2**.

### -field Size

The size of the structure, in bytes.  Should be ```sizeof(STOR_RICH_DEVICE_DESCRIPTION_V2)```.

### -field VendorId

A string representing the device’s vendor ID. May be an empty string if **ModelNumber** is provided. The miniport should fill this in.

### -field ModelNumber

A string representing the device’s model. The miniport should fill this in.

### -field FirmwareRevision

A string representing the device’s currently active firmware revision. The miniport should fill this in.

### -field Address

The address of the device for which the rich device description is desired. This is provided by Storport.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)
