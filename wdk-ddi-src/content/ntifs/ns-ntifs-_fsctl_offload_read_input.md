---
UID: NS:ntifs._FSCTL_OFFLOAD_READ_INPUT
title: FSCTL_OFFLOAD_READ_INPUT (ntifs.h)
description: Learn more about the FSCTL_OFFLOAD_READ_INPUT structure.
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["FSCTL_OFFLOAD_READ_INPUT structure"]
ms.keywords: "*PFSCTL_OFFLOAD_READ_INPUT, FSCTL_OFFLOAD_READ_INPUT, FSCTL_OFFLOAD_READ_INPUT structure [Installable File System Drivers], PFSCTL_OFFLOAD_READ_INPUT, PFSCTL_OFFLOAD_READ_INPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_READ_INPUT, ifsk.fsctl_offload_read_input, ntifs/FSCTL_OFFLOAD_READ_INPUT, ntifs/PFSCTL_OFFLOAD_READ_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: FSCTL_OFFLOAD_READ_INPUT, *PFSCTL_OFFLOAD_READ_INPUT
f1_keywords:
 - _FSCTL_OFFLOAD_READ_INPUT
 - ntifs/_FSCTL_OFFLOAD_READ_INPUT
 - PFSCTL_OFFLOAD_READ_INPUT
 - ntifs/PFSCTL_OFFLOAD_READ_INPUT
 - FSCTL_OFFLOAD_READ_INPUT
 - ntifs/FSCTL_OFFLOAD_READ_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FSCTL_OFFLOAD_READ_INPUT
 - PFSCTL_OFFLOAD_READ_INPUT
 - FSCTL_OFFLOAD_READ_INPUT
---

# FSCTL_OFFLOAD_READ_INPUT structure

## -description

The **FSCTL_OFFLOAD_READ_INPUT** structure contains the input for the [**FSCTL_OFFLOAD_READ**](/windows-hardware/drivers/ifs/fsctl-offload-read) control code request.

## -struct-fields

### -field Size

The size in bytes of this structure. Set this member to ```sizeof(FSCTL_OFFLOAD_READ_INPUT)```.

### -field Flags

 This member is not used. Set to 0.

### -field TokenTimeToLive

The time, in milliseconds, for which the read operation remains valid. The default time-to-live is 0. The recommended value for time-to-live is also 0.

### -field Reserved

 Reserved.

### -field FileOffset

 The position in the file to start reading from. The offset value must be aligned to a logical sector boundary on the volume.

### -field CopyLength

 The length, in bytes, of data to read, starting at **FileOffset**. The length  value must align to a logical sector boundary on the volume, except when the length matches end-of-file.

## -remarks

The  storage device's copy provider retains the data read for the duration in **TokenTimeToLive**. Multiple writes with the same token can be performed until the time in **TokenTimeToLive** expires.

## -see-also

[**FSCTL_OFFLOAD_READ**](/windows-hardware/drivers/ifs/fsctl-offload-read)

[**FSCTL_OFFLOAD_READ_OUTPUT**](ns-ntifs-_fsctl_offload_read_output.md)
