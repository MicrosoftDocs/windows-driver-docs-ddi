---
UID: NE:wdm._DRIVER_REGKEY_TYPE
title: DRIVER_REGKEY_TYPE
description: "Learn more about: DRIVER_REGKEY_TYPE enumeration"
tech.root: kernel
ms.date: 08/19/2019
keywords: ["DRIVER_REGKEY_TYPE enumeration"]
ms.keywords: DRIVER_REGKEY_TYPE, DRIVER_REGKEY_TYPE, *PDRIVER_REGKEY_TYPE,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DRIVER_REGKEY_TYPE, *PDRIVER_REGKEY_TYPE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DRIVER_REGKEY_TYPE
 - wdm/_DRIVER_REGKEY_TYPE
 - PDRIVER_REGKEY_TYPE
 - wdm/PDRIVER_REGKEY_TYPE
 - DRIVER_REGKEY_TYPE
 - wdm/DRIVER_REGKEY_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_REGKEY_TYPE
 - PDRIVER_REGKEY_TYPE
 - DRIVER_REGKEY_TYPE
---

# DRIVER_REGKEY_TYPE enumeration


## -description

Defines values for the type of registry key to be used by a driver.  This enumeration is used by the [**IoOpenDriverRegistryKey**](nf-wdm-ioopendriverregistrykey.md) function.

## -enum-fields

### -field DriverRegKeyParameters

The requested registry key is the immutable parameters key for the driver.

### -field DriverRegKeyPersistentState 

The requested registry key is a location for mutable state to be read/written that will persist across reboots. This mutable state is specific to the internals of the driver and only accessible by the driver itself.

### -field DriverRegKeySharedPersistentState 

The requested registry key is a location for mutable state to be read/written that will persist across reboots. This mutable state is meant to be shared between the driver and other components. Other components can access this registry key using GetSharedServiceRegistryStateKey. This value is available on Windows Server 2022 and later versions of Windows.

## -remarks

## -see-also

[**IoOpenDriverRegistryKey**](nf-wdm-ioopendriverregistrykey.md)

