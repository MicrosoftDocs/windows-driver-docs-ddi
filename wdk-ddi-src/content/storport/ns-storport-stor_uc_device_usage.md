---
UID: NS:storport._STOR_UC_DEVICE_USAGE
tech.root: storage
title: STOR_UC_DEVICE_USAGE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_UC_DEVICE_USAGE is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitUsage.
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
req.typenames: STOR_UC_DEVICE_USAGE, *PSTOR_UC_DEVICE_USAGE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_UC_DEVICE_USAGE
 - PSTOR_UC_DEVICE_USAGE
 - STOR_UC_DEVICE_USAGE
f1_keywords:
 - _STOR_UC_DEVICE_USAGE
 - storport/_STOR_UC_DEVICE_USAGE
 - PSTOR_UC_DEVICE_USAGE
 - storport/PSTOR_UC_DEVICE_USAGE
 - STOR_UC_DEVICE_USAGE
 - storport/STOR_UC_DEVICE_USAGE
dev_langs:
 - c++
---

## -description

**STOR_UC_DEVICE_USAGE** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitUsage**.

## -struct-fields

### -field Address

The device address for the usage notification.

### -field UsageType

A [**SCSI_UC_DEVICE_USAGE_TYPE**](ne-storport-scsi_uc_device_usage_type.md) value specifying the usage type from a PnP device usage notification.

### -field InUse

**TRUE** if the unit is used for the type in **UsageType**. Otherwise, **FALSE**.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**SCSI_UC_DEVICE_USAGE_TYPE**](ne-storport-scsi_uc_device_usage_type.md)
