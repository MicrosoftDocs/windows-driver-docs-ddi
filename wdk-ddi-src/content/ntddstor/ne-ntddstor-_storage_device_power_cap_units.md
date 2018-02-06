---
UID: NE:ntddstor._STORAGE_DEVICE_POWER_CAP_UNITS
title: "_STORAGE_DEVICE_POWER_CAP_UNITS"
author: windows-driver-content
description: The units of the maximum power threshold.
old-location: storage\storage_device_power_cap_units.htm
old-project: storage
ms.assetid: 199900F4-90A7-4F2E-B85E-25BF3593D50B
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/StorageDevicePowerCapUnitsMilliwatts, StorageDevicePowerCapUnitsMilliwatts, *PSTORAGE_DEVICE_POWER_CAP_UNITS, storage.storage_device_power_cap_units, ntddstor/STORAGE_DEVICE_POWER_CAP_UNITS, STORAGE_DEVICE_POWER_CAP_UNITS enumeration [Storage Devices], _STORAGE_DEVICE_POWER_CAP_UNITS, STORAGE_DEVICE_POWER_CAP_UNITS, StorageDevicePowerCapUnitsPercent, ntddstor/StorageDevicePowerCapUnitsPercent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	ntddstor.h
apiname:
-	STORAGE_DEVICE_POWER_CAP_UNITS
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_POWER_CAP_UNITS, *PSTORAGE_DEVICE_POWER_CAP_UNITS
---

# _STORAGE_DEVICE_POWER_CAP_UNITS enumeration


## -description


The units of the maximum power threshold.


## -syntax


````
typedef enum _STORAGE_DEVICE_POWER_CAP_UNITS { 
  StorageDevicePowerCapUnitsPercent,
  StorageDevicePowerCapUnitsMilliwatts
} STORAGE_DEVICE_POWER_CAP_UNITS;
````


## -enum-fields




### -field StorageDevicePowerCapUnitsPercent

Units in percent.


### -field StorageDevicePowerCapUnitsMilliwatts

Units in milliwatts.

