---
UID: NS:ntdddisk._DRIVERSTATUS
title: _DRIVERSTATUS (ntdddisk.h)
description: The DRIVERSTATUS structure is used in conjunction with the SENDCMDOUTPARAMS structure and the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\driverstatus.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DRIVERSTATUS structure"]
ms.keywords: "*LPDRIVERSTATUS, *PDRIVERSTATUS, DRIVERSTATUS, DRIVERSTATUS structure [Storage Devices], LPDRIVERSTATUS, LPDRIVERSTATUS structure pointer [Storage Devices], PDRIVERSTATUS, PDRIVERSTATUS structure pointer [Storage Devices], _DRIVERSTATUS, ntdddisk/DRIVERSTATUS, ntdddisk/LPDRIVERSTATUS, ntdddisk/PDRIVERSTATUS, storage.driverstatus, structs-IDE_e49310ff-1d3c-44d5-a997-08b8f500ed13.xml"
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
req.typenames: DRIVERSTATUS, *PDRIVERSTATUS, *LPDRIVERSTATUS
f1_keywords:
 - _DRIVERSTATUS
 - ntdddisk/_DRIVERSTATUS
 - PDRIVERSTATUS
 - ntdddisk/PDRIVERSTATUS
 - DRIVERSTATUS
 - ntdddisk/DRIVERSTATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - DRIVERSTATUS
---

# _DRIVERSTATUS structure


## -description

The DRIVERSTATUS structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_sendcmdoutparams">SENDCMDOUTPARAMS</a> structure and the <a href="/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.

## -struct-fields

### -field bDriverError

Error code from driver, or 0 if no error.

### -field bIDEError

Contents of IDE Error register.

### -field bReserved

Reserved.

### -field dwReserved

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_sendcmdoutparams">SENDCMDOUTPARAMS</a>



<a href="/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a>
