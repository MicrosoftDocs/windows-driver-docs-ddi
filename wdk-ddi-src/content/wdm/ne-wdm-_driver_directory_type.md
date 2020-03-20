---
UID: NE:wdm._DRIVER_DIRECTORY_TYPE
title: _DRIVER_DIRECTORY_TYPE (wdm.h)
description: 
ms.assetid: 587aa860-ad2d-4de2-9f84-1ad5cb7b01bf
ms.date: 10/19/2018
keywords: ["_DRIVER_DIRECTORY_TYPE enumeration"]
f1_keywords:
 - "wdm/_DRIVER_DIRECTORY_TYPE"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- wdm.h
api_name: 
- _DRIVER_DIRECTORY_TYPE
product:
- Windows
targetos: Windows
---

# _DRIVER_DIRECTORY_TYPE enumeration

## -description

Defines values for the type of directory used by the driver to load and store files. This enumeration is used by the [**IoGetDriverDirectory**](nf-wdm-iogetdriverdirectory.md) function. The files in that directory apply to a specific driver object.

## -enum-fields

### -field DriverDirectoryImage
The directory from which the driver was loaded.

### -field DriverDirectoryData
The requested directory is a general-purpose directory in which the driver stores file that contains state-specific information to the internals of the driver.

## -remarks

## -see-also
[**IoGetDriverDirectory**](nf-wdm-iogetdriverdirectory.md)
