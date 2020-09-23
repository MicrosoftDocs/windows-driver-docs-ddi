---
UID: NS:storport._STOR_UNIT_CONTROL_QUERY_BUS_TYPE
title: STOR_UNIT_CONTROL_QUERY_BUS_TYPE
description: The STOR_UNIT_CONTROL_QUERY_BUS_TYPE structure is a parameter to a miniport driver for ScsiUnitQueryBusType, which the miniport can use to specify the device bus type.
tech.root: storage
ms.assetid: a4118e48-cf4c-456d-b191-032eafbcab0c
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: struct
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

The **STOR_UNIT_CONTROL_QUERY_BUS_TYPE** structure is a parameter to a miniport driver for ScsiUnitQueryBusType, which the miniport can use to specify the device bus type.

## -struct-fields

### -field Address

Pointer to a [**STOR_ADDRESS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_stor_address) structure that holds a storage device address.

### -field BusType

The bus type specified by the miniport for the unit. This value must be one of the enum values defined in [**STORAGE_BUS_TYPE**](https://docs.microsoft.com/windows/win32/api/winioctl/ne-winioctl-storage_bus_type).

## -remarks

ScsiUnitQueryBusType is optional. A miniport can use it to specify a device bus type if the device and controller have different bus types.

## -see-also

[**STOR_ADDRESS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_stor_address)

[**STORAGE_BUS_TYPE**](https://docs.microsoft.com/windows/win32/api/winioctl/ne-winioctl-storage_bus_type)

