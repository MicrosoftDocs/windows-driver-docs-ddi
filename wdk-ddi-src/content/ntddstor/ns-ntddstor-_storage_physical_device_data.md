---
UID: NS:ntddstor._STORAGE_PHYSICAL_DEVICE_DATA
title: _STORAGE_PHYSICAL_DEVICE_DATA (ntddstor.h)
description: Specifies the physical device data of a storage device.
old-location: storage\storage_physical_device_data.htm
tech.root: storage
ms.assetid: 9D8E67D1-EB7C-4EED-8BDD-43D5E012B99C
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_PHYSICAL_DEVICE_DATA, PSTORAGE_PHYSICAL_DEVICE_DATA, PSTORAGE_PHYSICAL_DEVICE_DATA structure pointer [Storage Devices], STORAGE_PHYSICAL_DEVICE_DATA, STORAGE_PHYSICAL_DEVICE_DATA structure [Storage Devices], _STORAGE_PHYSICAL_DEVICE_DATA, ntddstor/PSTORAGE_PHYSICAL_DEVICE_DATA, ntddstor/STORAGE_PHYSICAL_DEVICE_DATA, storage.storage_physical_device_data"
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_PHYSICAL_DEVICE_DATA"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- Ntddstor.h
api_name:
- STORAGE_PHYSICAL_DEVICE_DATA
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PHYSICAL_DEVICE_DATA, *PSTORAGE_PHYSICAL_DEVICE_DATA
---

# _STORAGE_PHYSICAL_DEVICE_DATA structure


## -description


Specifies the physical device data of a storage device.


## -struct-fields




### -field DeviceId

The hardware ID of the storage device.


### -field Role

The role of the storage device. A bitmask can be use to specify multiple roles, including <b>STORAGE_COMPONENT_ROLE_CACHE</b> (0x00000001), <b>STORAGE_COMPONENT_ROLE_TIERING</b> (0x00000002), and <b>STORAGE_COMPONENT_ROLE_DATA</b> (0x00000004).


### -field HealthStatus

Indicates the health status of a storage device, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-_storage_component_health_status">STORAGE_COMPONENT_HEALTH_STATUS</a>.


### -field CommandProtocol

Specifies the storage command protocols that are used between software and hardware, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-_storage_protocol_type">STORAGE_PROTOCOL_TYPE</a>.


### -field SpecVersion

Indicates the specification of the storage device, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_spec_version">STORAGE_SPEC_VERSION</a>.


### -field FormFactor

Indicates the form factor of a storage device, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-_storage_device_form_factor">STORAGE_DEVICE_FORM_FACTOR</a>.


### -field Vendor

 


### -field Model

 


### -field FirmwareRevision

 


### -field Capacity

The capacity of the storage device in units of kilobytes (1024 bytes).


### -field PhysicalLocation

 


### -field Reserved

 




#### - FirmwareRevision[16]

The revision number of the storage device.


#### - Model[40]

The model name of the storage device.


#### - PhysicalLocation[32]

This member is reserved for future use.


#### - Reserved[2]

Specifies if the storage device is reserved.


#### - Vendor[8]

The vendor name of the storage device.

