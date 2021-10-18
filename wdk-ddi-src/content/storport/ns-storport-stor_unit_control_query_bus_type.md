---
UID: NS:storport._STOR_UNIT_CONTROL_QUERY_BUS_TYPE
title: STOR_UNIT_CONTROL_QUERY_BUS_TYPE
description: STOR_UNIT_CONTROL_QUERY_BUS_TYPE is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitQueryBusType.
tech.root: storage
ms.date: 05/13/2021
ms.keywords: STOR_UNIT_CONTROL_QUERY_BUS_TYPE, STOR_UNIT_CONTROL_QUERY_BUS_TYPE, *PSTOR_UNIT_CONTROL_QUERY_BUS_TYPE,
req.header: storport.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: STOR_UNIT_CONTROL_QUERY_BUS_TYPE, *PSTOR_UNIT_CONTROL_QUERY_BUS_TYPE
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - PSTOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - STOR_UNIT_CONTROL_QUERY_BUS_TYPE
product:
 - Windows
f1_keywords:
 - _STOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - storport/_STOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - PSTOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - storport/PSTOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - STOR_UNIT_CONTROL_QUERY_BUS_TYPE
 - storport/STOR_UNIT_CONTROL_QUERY_BUS_TYPE
---

# STOR_UNIT_CONTROL_QUERY_BUS_TYPE structure

## -description

**STOR_UNIT_CONTROL_QUERY_BUS_TYPE** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitQueryBusType**.

## -struct-fields

### -field Address

Pointer to a [**STOR_ADDRESS**](../scsi/ns-scsi-_stor_address.md) structure that holds a storage device address.

### -field BusType

The bus type specified by the miniport for the unit. This value must be one of the enum values defined in [**STORAGE_BUS_TYPE**](../ntddstor/ne-ntddstor-storage_bus_type.md).

## -remarks

A miniport can use it to specify a device bus type if the device and controller have different bus types.

## -see-also

[**STOR_ADDRESS**](../scsi/ns-scsi-_stor_address.md)

[**STORAGE_BUS_TYPE**](../ntddstor/ne-ntddstor-storage_bus_type.md)
