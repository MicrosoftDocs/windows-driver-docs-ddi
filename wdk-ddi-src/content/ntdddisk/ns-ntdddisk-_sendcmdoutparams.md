---
UID: NS:ntdddisk._SENDCMDOUTPARAMS
title: SENDCMDOUTPARAMS (ntdddisk.h)
description: The SENDCMDOUTPARAMS structure is used in conjunction with the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\sendcmdoutparams.htm
tech.root: storage
ms.date: 07/14/2022
keywords: ["SENDCMDOUTPARAMS structure"]
ms.keywords: "*LPSENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS structure pointer [Storage Devices], PSENDCMDOUTPARAMS, PSENDCMDOUTPARAMS structure pointer [Storage Devices], SENDCMDOUTPARAMS, SENDCMDOUTPARAMS structure [Storage Devices], _SENDCMDOUTPARAMS, ntdddisk/LPSENDCMDOUTPARAMS, ntdddisk/PSENDCMDOUTPARAMS, ntdddisk/SENDCMDOUTPARAMS, storage.sendcmdoutparams, structs-IDE_d1a70016-0e77-465a-9368-665975369bdc.xml"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
targetos: Windows
req.typenames: SENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, *LPSENDCMDOUTPARAMS
f1_keywords:
 - _SENDCMDOUTPARAMS
 - ntdddisk/_SENDCMDOUTPARAMS
 - PSENDCMDOUTPARAMS
 - ntdddisk/PSENDCMDOUTPARAMS
 - SENDCMDOUTPARAMS
 - ntdddisk/SENDCMDOUTPARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _SENDCMDOUTPARAMS
 - PSENDCMDOUTPARAMS
 - SENDCMDOUTPARAMS
---

# SENDCMDOUTPARAMS structure

## -description

The **SENDCMDOUTPARAMS** structure is used in conjunction with the **SMART_SEND_DRIVE_COMMAND** request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.

## -struct-fields

### -field cBufferSize

Contains the size in bytes of the buffer pointed to by **bBuffer**.

### -field DriverStatus

Contains a [**DRIVERSTATUS**](ns-ntdddisk-_driverstatus.md) structure that indicates the driver status.

### -field bBuffer

Pointer to a buffer in which to store the data read from the drive.

## -remarks

The **SENDCMDOUTPARAMS** structure is used with the **SMART_SEND_DRIVE_COMMAND** and **SMART_RCV_DRIVE_DATA** I/O control code requests. See the Remarks section of [**SENDCMDINPARAMS**](ns-ntdddisk-_sendcmdinparams.md) for details about these requests.

## -see-also

[**SENDCMDINPARAMS**](ns-ntdddisk-_sendcmdinparams.md)
