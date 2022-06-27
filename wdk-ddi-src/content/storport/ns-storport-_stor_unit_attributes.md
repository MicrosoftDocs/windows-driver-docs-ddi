---
UID: NS:storport._STOR_UNIT_ATTRIBUTES
title: STOR_UNIT_ATTRIBUTES (storport.h)
description: The STOR_UNIT_ATTRIBUTES structure contains bitfields indicating attribute support for a storage device unit.
old-location: storage\stor_unit_attributes.htm
tech.root: storage
ms.date: 05/24/2022
keywords: ["STOR_UNIT_ATTRIBUTES structure"]
ms.keywords: "*PSTOR_UNIT_ATTRIBUTES, PSTOR_UNIT_ATTRIBUTES, PSTOR_UNIT_ATTRIBUTES structure pointer [Storage Devices], STOR_UNIT_ATTRIBUTES, STOR_UNIT_ATTRIBUTES structure [Storage Devices], _STOR_UNIT_ATTRIBUTES, storage.stor_unit_attributes, storport/PSTOR_UNIT_ATTRIBUTES, storport/STOR_UNIT_ATTRIBUTES"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: STOR_UNIT_ATTRIBUTES, *PSTOR_UNIT_ATTRIBUTES
f1_keywords:
 - _STOR_UNIT_ATTRIBUTES
 - storport/_STOR_UNIT_ATTRIBUTES
 - PSTOR_UNIT_ATTRIBUTES
 - storport/PSTOR_UNIT_ATTRIBUTES
 - STOR_UNIT_ATTRIBUTES
 - storport/STOR_UNIT_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - _STOR_UNIT_ATTRIBUTES
 - PSTOR_UNIT_ATTRIBUTES
 - STOR_UNIT_ATTRIBUTES
---

# STOR_UNIT_ATTRIBUTES structure

## -description

The **STOR_UNIT_ATTRIBUTES** structure contains bitfields indicating attribute support for a storage device unit.

## -struct-fields

### -field DeviceAttentionSupported

Set to 1 if device attention is supported for the unit. Otherwise, set to 0.

### -field AsyncNotificationSupported

Set to 1 if the device supports asynchronous notifications. Otherwise, set to 0.

### -field D3ColdNotSupported

Set to 1 if the D3 Cold power state is NOT supported. Otherwise, set to 0.

### -field BypassIOSupported

Set to 1 if [BypassIO](/windows-hardware/drivers/storage/bypassio) is supported for the unit. Otherwise, set to 0.

### -field Reserved

Reserved bits. Must be set to 0.

## -remarks

The unit attributes are registered with Storport using this structure as a parameter to the [**StorPortSetUnitAttributes**](nf-storport-storportsetunitattributes.md) routine.

If the miniport driver supports asynchronous notifications, the **AsyncNotificationSupported** field set to 1, it will send notifications to the Storport driver using the [**StorPortAsyncNotificationDetected**](nf-storport-storportasyncnotificationdetected.md) routine.

## -see-also

[**StorPortAsyncNotificationDetected**](nf-storport-storportasyncnotificationdetected.md)

[**StorPortSetUnitAttributes**](nf-storport-storportsetunitattributes.md)
