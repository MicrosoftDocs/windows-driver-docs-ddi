---
UID: NE:wdm._DRIVER_DIRECTORY_TYPE
title: _DRIVER_DIRECTORY_TYPE (wdm.h)
description: 
ms.assetid: 587aa860-ad2d-4de2-9f84-1ad5cb7b01bf
ms.date: 10/19/2018
keywords: ["DRIVER_DIRECTORY_TYPE enumeration"]
ms.keywords: _DRIVER_DIRECTORY_TYPE, DRIVER_DIRECTORY_TYPE, *PDRIVER_DIRECTORY_TYPE,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DRIVER_DIRECTORY_TYPE, *PDRIVER_DIRECTORY_TYPE
targetos: Windows
f1_keywords:
 - _DRIVER_DIRECTORY_TYPE
 - wdm/_DRIVER_DIRECTORY_TYPE
 - PDRIVER_DIRECTORY_TYPE
 - wdm/PDRIVER_DIRECTORY_TYPE
 - DRIVER_DIRECTORY_TYPE
 - wdm/DRIVER_DIRECTORY_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_DIRECTORY_TYPE
---

# _DRIVER_DIRECTORY_TYPE enumeration


## -description

Defines values for the type of directory used by the driver to load and store files. This enumeration is used by the [**IoGetDriverDirectory**](nf-wdm-iogetdriverdirectory.md) function. The files in that directory apply to a specific driver object.

## -enum-fields

### -field DriverDirectoryImage

The directory from which the driver was loaded.

### -field DriverDirectoryData
The requested directory is a general-purpose directory in which the driver stores files that contain state information specific to the internals of the driver and only used by the driver itself.

### -field DriverDirectorySharedData
The requested directory is a general-purpose directory in which the driver stores or reads files that contain state information that is meant to be shared between the driver and other components. Other components can access this directory using GetSharedServiceDirectory. This value is available on Windows Iron and later versions of Windows.

## -remarks

## -see-also

[**IoGetDriverDirectory**](nf-wdm-iogetdriverdirectory.md)

