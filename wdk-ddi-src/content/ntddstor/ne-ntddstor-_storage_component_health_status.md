---
UID: NE:ntddstor._STORAGE_COMPONENT_HEALTH_STATUS
title: "_STORAGE_COMPONENT_HEALTH_STATUS"
author: windows-driver-content
description: Indicates the health status of a storage device.
old-location: storage\storage_component_health_status.htm
old-project: storage
ms.assetid: 6768C1D7-A964-44A7-A340-98060130FF24
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HealthStatusDisabled, HealthStatusFailed, ntddstor/HealthStatusDisabled, ntddstor/HealthStatusThrottled, STORAGE_COMPONENT_HEALTH_STATUS, HealthStatusNormal, ntddstor/STORAGE_COMPONENT_HEALTH_STATUS, _STORAGE_COMPONENT_HEALTH_STATUS, STORAGE_COMPONENT_HEALTH_STATUS enumeration [Storage Devices], HealthStatusWarning, ntddstor/HealthStatusUnknown, ntddstor/HealthStatusNormal, ntddstor/HealthStatusWarning, ntddstor/PSTORAGE_COMPONENT_HEALTH_STATUS, HealthStatusThrottled, storage.storage_component_health_status, PSTORAGE_COMPONENT_HEALTH_STATUS, HealthStatusUnknown, PSTORAGE_COMPONENT_HEALTH_STATUS enumeration pointer [Storage Devices], ntddstor/HealthStatusFailed, *PSTORAGE_COMPONENT_HEALTH_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	STORAGE_COMPONENT_HEALTH_STATUS
product: Windows
targetos: Windows
req.typenames: STORAGE_COMPONENT_HEALTH_STATUS, *PSTORAGE_COMPONENT_HEALTH_STATUS
---

# _STORAGE_COMPONENT_HEALTH_STATUS enumeration


## -description


Indicates the health status of a storage device.


## -syntax


````
typedef enum _STORAGE_COMPONENT_HEALTH_STATUS { 
  HealthStatusUnknown    = 0, // 0x0
  HealthStatusNormal,
  HealthStatusThrottled,
  HealthStatusWarning,
  HealthStatusDisabled,
  HealthStatusFailed
} STORAGE_COMPONENT_HEALTH_STATUS, *PSTORAGE_COMPONENT_HEALTH_STATUS;
````


## -enum-fields




### -field HealthStatusUnknown

The storage device health status is unknown.


### -field HealthStatusNormal

The storage device is operating normally.


### -field HealthStatusThrottled

The storage device has been throttled.


### -field HealthStatusWarning

The storage device has issued a warning.


### -field HealthStatusDisabled

The storage device has been disabled.


### -field HealthStatusFailed

The storage device has failed.

