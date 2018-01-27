---
UID: NS:ntddstor._STORAGE_PHYSICAL_ADAPTER_DATA
title: _STORAGE_PHYSICAL_ADAPTER_DATA
author: windows-driver-content
description: Specifies the physical device data of a storage adapter.
old-location: storage\storage_physical_adapter_data.htm
old-project: storage
ms.assetid: 404A7AFC-291E-4056-9076-F9E62A07C9FB
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSTORAGE_PHYSICAL_ADAPTER_DATA structure pointer [Storage Devices], ntddstor/STORAGE_PHYSICAL_ADAPTER_DATA, STORAGE_PHYSICAL_ADAPTER_DATA, ntddstor/PSTORAGE_PHYSICAL_ADAPTER_DATA, STORAGE_PHYSICAL_ADAPTER_DATA structure [Storage Devices], *PSTORAGE_PHYSICAL_ADAPTER_DATA, _STORAGE_PHYSICAL_ADAPTER_DATA, PSTORAGE_PHYSICAL_ADAPTER_DATA, storage.storage_physical_adapter_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddstor.h
apiname: 
-	STORAGE_PHYSICAL_ADAPTER_DATA
product: Windows
targetos: Windows
req.typenames: *PSTORAGE_PHYSICAL_ADAPTER_DATA, STORAGE_PHYSICAL_ADAPTER_DATA
---

# _STORAGE_PHYSICAL_ADAPTER_DATA structure


## -description


Specifies the physical device data of a storage adapter.


## -syntax


````
typedef struct _STORAGE_PHYSICAL_ADAPTER_DATA {
  ULONG                           AdapterId;
  STORAGE_COMPONENT_HEALTH_STATUS HealthStatus;
  STORAGE_PROTOCOL_TYPE           CommandProtocol;
  STORAGE_SPEC_VERSION            SpecVersion;
  UCHAR                           Vendor[8];
  UCHAR                           Model[40];
  UCHAR                           FirmwareRevision[16];
  UCHAR                           PhysicalLocation[32];
  BOOLEAN                         ExpandedConnector;
  UCHAR                           Reserved0[3];
  ULONG                           Reserved1[3];
} STORAGE_PHYSICAL_ADAPTER_DATA, *PSTORAGE_PHYSICAL_ADAPTER_DATA;
````


## -struct-fields




### -field AdapterId

The hardware ID of the storage adapter.


### -field HealthStatus

Indicates the health status of a storage adapter, of type <a href="..\ntddstor\ne-ntddstor-_storage_component_health_status.md">STORAGE_COMPONENT_HEALTH_STATUS</a>.


### -field CommandProtocol

Specifies the storage command protocols that are used between software and hardware, of type <a href="..\ntddstor\ne-ntddstor-_storage_protocol_type.md">STORAGE_PROTOCOL_TYPE</a>.


### -field SpecVersion

Indicates the specification of the storage adapter, of type <a href="..\ntddstor\ns-ntddstor-_storage_spec_version.md">STORAGE_SPEC_VERSION</a>.


### -field Vendor

 


### -field Model

 


### -field FirmwareRevision

 


### -field PhysicalLocation

 


### -field ExpanderConnected

 


### -field Reserved0

 


### -field Reserved1

 



#### - PhysicalLocation[32]

This member is reserved for future use.


#### - ExpandedConnector

Specifies if the storage adapter includes an expanded connector.


#### - FirmwareRevision[16]

The revision number of the storage adapter.


#### - Vendor[8]

The vendor name of the storage adapter.


#### - Reserved1[3]

Specifies if the storage adapter is reserved.


#### - Reserved0[3]

Specifies if the storage adapter is reserved.


#### - Model[40]

The model name of the storage adapter.

