---
UID: NS:ntdddisk._SENDCMDINPARAMS
title: _SENDCMDINPARAMS (ntdddisk.h)
description: The SENDCMDINPARAMS structure contains the input parameters for the SMART_SEND_DRIVE_COMMAND request.
old-location: storage\sendcmdinparams.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SENDCMDINPARAMS structure"]
ms.keywords: "*LPSENDCMDINPARAMS, *PSENDCMDINPARAMS, LPSENDCMDINPARAMS, LPSENDCMDINPARAMS structure pointer [Storage Devices], PSENDCMDINPARAMS, PSENDCMDINPARAMS structure pointer [Storage Devices], SENDCMDINPARAMS, SENDCMDINPARAMS structure [Storage Devices], _SENDCMDINPARAMS, ntdddisk/LPSENDCMDINPARAMS, ntdddisk/PSENDCMDINPARAMS, ntdddisk/SENDCMDINPARAMS, storage.sendcmdinparams, structs-IDE_b80faf9d-dfcf-4eac-b0be-fb18964c4c2b.xml"
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
req.typenames: SENDCMDINPARAMS, *PSENDCMDINPARAMS, *LPSENDCMDINPARAMS
f1_keywords:
 - _SENDCMDINPARAMS
 - ntdddisk/_SENDCMDINPARAMS
 - PSENDCMDINPARAMS
 - ntdddisk/PSENDCMDINPARAMS
 - SENDCMDINPARAMS
 - ntdddisk/SENDCMDINPARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _SENDCMDINPARAMS
 - PSENDCMDINPARAMS
 - SENDCMDINPARAMS
---

# _SENDCMDINPARAMS structure


## -description

The SENDCMDINPARAMS structure contains the input parameters for the <a href="/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a> request.

## -struct-fields

### -field cBufferSize

Contains the buffer size, in bytes.

### -field irDriveRegs

Contains a <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_ideregs">IDEREGS</a> structure used to report the contents of the IDE controller registers.

### -field bDriveNumber

The <b>bDriveNumber</b> member is opaque. Do not use it. The operating system ignores this member, because the physical drive that receives the request depends on the handle that the caller uses when making the request.

### -field bReserved

Reserved.

### -field dwReserved

Reserved.

### -field bBuffer

Pointer to the input buffer.

## -remarks

The <a href="/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a> is used to send a Self-Monitoring Analysis and Reporting Technology (SMART) commands to a device. 

The SENDCMDINPARAMS structure is also used with the <a href="/previous-versions/windows/hardware/drivers/ff566204(v=vs.85)">SMART_RCV_DRIVE_DATA</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_sendcmdoutparams">SENDCMDOUTPARAMS</a>



<a href="/previous-versions/windows/hardware/drivers/ff566204(v=vs.85)">SMART_RCV_DRIVE_DATA</a>



<a href="/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a>

