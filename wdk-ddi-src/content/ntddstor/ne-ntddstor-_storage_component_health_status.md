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
ms.keywords: ntddstor/HealthStatusThrottled, ntddstor/HealthStatusUnknown, HealthStatusFailed, ntddstor/HealthStatusNormal, HealthStatusUnknown, HealthStatusThrottled, ntddstor/STORAGE_COMPONENT_HEALTH_STATUS, _STORAGE_COMPONENT_HEALTH_STATUS, ntddstor/HealthStatusWarning, storage.storage_component_health_status, ntddstor/HealthStatusDisabled, STORAGE_COMPONENT_HEALTH_STATUS, PSTORAGE_COMPONENT_HEALTH_STATUS, HealthStatusDisabled, ntddstor/PSTORAGE_COMPONENT_HEALTH_STATUS, HealthStatusWarning, PSTORAGE_COMPONENT_HEALTH_STATUS enumeration pointer [Storage Devices], *PSTORAGE_COMPONENT_HEALTH_STATUS, ntddstor/HealthStatusFailed, STORAGE_COMPONENT_HEALTH_STATUS enumeration [Storage Devices], HealthStatusNormal
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




#### - HealthStatusUnknown

The storage device health status is unknown.


#### - HealthStatusNormal

The storage device is operating normally.


#### - HealthStatusThrottled

The storage device has been throttled.


#### - HealthStatusWarning

The storage device has issued a warning.


#### - HealthStatusDisabled

The storage device has been disabled.


#### - HealthStatusFailed

The storage device has failed.

