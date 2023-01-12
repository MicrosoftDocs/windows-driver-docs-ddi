---
UID: NS:ntdddisk._GETVERSIONINPARAMS
title: GETVERSIONINPARAMS (ntdddisk.h)
description: The GETVERSIONINPARAMS structure is used in conjunction with the SMART_GET_VERSION request to retrieve version information, a capabilities mask, and a bitmask for the indicated device.
old-location: storage\getversioninparams.htm
tech.root: storage
ms.date: 07/14/2022
keywords: ["GETVERSIONINPARAMS structure"]
ms.keywords: "*LPGETVERSIONINPARAMS, *PGETVERSIONINPARAMS, GETVERSIONINPARAMS, GETVERSIONINPARAMS structure [Storage Devices], LPGETVERSIONINPARAMS, LPGETVERSIONINPARAMS structure pointer [Storage Devices], PGETVERSIONINPARAMS, PGETVERSIONINPARAMS structure pointer [Storage Devices], _GETVERSIONINPARAMS, ntdddisk/GETVERSIONINPARAMS, ntdddisk/LPGETVERSIONINPARAMS, ntdddisk/PGETVERSIONINPARAMS, storage.getversioninparams, structs-IDE_5426037d-a75f-4b92-a935-e467d02ec8c7.xml"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000
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
req.typenames: GETVERSIONINPARAMS, *PGETVERSIONINPARAMS, *LPGETVERSIONINPARAMS
f1_keywords:
 - _GETVERSIONINPARAMS
 - ntdddisk/_GETVERSIONINPARAMS
 - PGETVERSIONINPARAMS
 - ntdddisk/PGETVERSIONINPARAMS
 - GETVERSIONINPARAMS
 - ntdddisk/GETVERSIONINPARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _GETVERSIONINPARAMS
 - PGETVERSIONINPARAMS
 - GETVERSIONINPARAMS
---

# GETVERSIONINPARAMS structure

## -description

The GETVERSIONINPARAMS structure is used in conjunction with the **SMART_GET_VERSION** request to retrieve version information, a capabilities mask, and a bitmask for the indicated device.

## -struct-fields

### -field bVersion

Contains an integer that indicates the version number of the binary driver.

### -field bRevision

Contains an integer that indicates the revision number of the binary driver.

### -field bReserved

Reserved.

### -field bIDEDeviceMap

Contains the bitmap. The following table explains the meaning of the bitmap:

| Bitmap Flags | Meaning |
| ------------ | ------- |
| Bit 0 is set to 1. | The device is either a SATA drive or an IDE drive. If it is an IDE drive, it is the master device on the primary channel. |
| Bit 1 is set to 1. | The device is an IDE drive, and it is the subordinate device on the primary channel. |
| Bit 2 is set to 1. | The device is an IDE drive, and it is the master device on the secondary channel. |
| Bit 3 is set to 1. | The device is an IDE drive, and it is the subordinate device on the secondary channel. |
| Bit 4 is set to 1. | The device is an ATAPI drive, and it is the master device on the primary channel. |
| Bit 5 is set to 1. | The device is an ATAPI drive, and it is the subordinate device on the primary channel. |
| Bit 6 is set to 1. | The device is an ATAPI drive, and it is the master device on the secondary channel. |
| Bit 7 is set to 1. | The device is an ATAPI drive, and it is the subordinate device on the secondary channel. |

### -field fCapabilities

Contains the bitmask of driver capabilities.

| Bitmap Flags | Meaning |
| ------------ | ------- |
| CAP_ATA_ID_CMD   | The device supports the ATA ID command. |
| CAP_ATAPI_ID_CMD | The device supports the ATAPI ID command. |
| CAP_SMART_CMD    | The device supports SMART commands. |

### -field dwReserved

Reserved.

## -remarks

The **SMART_GET_VERSION** control code returns version information, a capabilities mask, and a bitmask for the device. This IOCTL must be handled by drivers that support Self-Monitoring Analysis and Reporting Technology (SMART).

* Input Parameters

  **Parameters.DeviceIoControl.OutputBufferLength** indicates the size, in bytes, of the buffer, which must be >= sizeof(GETVERSIONINPARAMS).

* Output Parameters

  The driver returns the information to the buffer at Irp->AssociatedIrp.SystemBuffer.

* I/O Status Block

  The driver sets the Information field to sizeof(GETVERSIONINPARAMS) when it sets the Status field to STATUS_SUCCESS. Otherwise, the driver sets the Information field to zero and sets the Status field to possibly STATUS_INVALID_PARAMETER.
