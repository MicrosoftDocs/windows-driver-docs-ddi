---
UID: NE:storport._SCSI_UC_DEVICE_USAGE_TYPE
tech.root: storage
title: SCSI_UC_DEVICE_USAGE_TYPE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: SCSI_UC_DEVICE_USAGE_TYPE specifies the device usage type from a PnP device usage notification.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _SCSI_UC_DEVICE_USAGE_TYPE
 - SCSI_UC_DEVICE_USAGE_TYPE
f1_keywords:
 - _SCSI_UC_DEVICE_USAGE_TYPE
 - storport/_SCSI_UC_DEVICE_USAGE_TYPE
 - SCSI_UC_DEVICE_USAGE_TYPE
 - storport/SCSI_UC_DEVICE_USAGE_TYPE
dev_langs:
 - c++
---

## -description

**SCSI_UC_DEVICE_USAGE_TYPE** specifies the device usage type from a PnP device usage notification.

## -enum-fields

### -field ScsiDeviceUsageTypeUndefined

The device usage type is undefined.

### -field ScsiDeviceUsageTypePaging

The page file will be used on the device.

### -field ScsiDeviceUsageTypeHibernation

The hibernation file will be used on the device.

### -field ScsiDeviceUsageTypeDumpFile

The dump file will be used on the device.

### -field ScsiDeviceUsageTypeBoot

The device is used to boot the operating system.

## -remarks

**SCSI_UC_DEVICE_USAGE_TYPE** is a member of the [**STOR_UC_DEVICE_USAGE**](ns-storport-stor_uc_device_usage.md) structure, which Storport uses when it calls a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine with a **ControlType** of **ScsiUnitUsage**.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_UC_DEVICE_USAGE**](ns-storport-stor_uc_device_usage.md)
