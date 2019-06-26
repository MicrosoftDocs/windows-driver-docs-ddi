---
UID: NS:ntifs._FSCTL_OFFLOAD_READ_INPUT
title: _FSCTL_OFFLOAD_READ_INPUT (ntifs.h)
description: The FSCTL_OFFLOAD_READ_INPUT structure contains the input for the FSCTL_OFFLOAD_READ control code request.
old-location: ifsk\fsctl_offload_read_input.htm
tech.root: ifsk
ms.assetid: 11F9FFC6-D2F6-4CCA-9459-CF2639AE652D
ms.date: 04/16/2018
ms.keywords: "*PFSCTL_OFFLOAD_READ_INPUT, FSCTL_OFFLOAD_READ_INPUT, FSCTL_OFFLOAD_READ_INPUT structure [Installable File System Drivers], PFSCTL_OFFLOAD_READ_INPUT, PFSCTL_OFFLOAD_READ_INPUT structure pointer [Installable File System Drivers], _FSCTL_OFFLOAD_READ_INPUT, ifsk.fsctl_offload_read_input, ntifs/FSCTL_OFFLOAD_READ_INPUT, ntifs/PFSCTL_OFFLOAD_READ_INPUT"
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FSCTL_OFFLOAD_READ_INPUT
product:
- Windows
targetos: Windows
req.typenames: FSCTL_OFFLOAD_READ_INPUT, *PFSCTL_OFFLOAD_READ_INPUT
---

# _FSCTL_OFFLOAD_READ_INPUT structure


## -description


The <b>FSCTL_OFFLOAD_READ_INPUT</b> structure contains the input for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-offload-read">FSCTL_OFFLOAD_READ</a> control code request.


## -struct-fields




### -field Size

The size of this structure. Set this member to <b>sizeof</b>(FSCTL_OFFLOAD_READ_INPUT).


### -field Flags

 This member is not used. Set to 0.


### -field TokenTimeToLive

The time, in milliseconds, for which the read operation remains valid. The default time-to-live is 0. The recommended value for time-to-live is also 0.


### -field Reserved

 Reserved.


### -field FileOffset

 The position in the file to start reading from. The offset value must be aligned to a logical sector boundary on the volume.


### -field CopyLength

 




#### - Length

 The length, in bytes, of data to read, starting at <b>FileOffset</b>. The length  value must align to a logical sector boundary on the volume, except when the length matches end-of-file.


## -remarks



The  storage device's copy provider retains the data read for the duration in <b>TokenTimeToLive</b>. Multiple writes with the same token can be performed until the time in <b>TokenTimeToLive</b> expires.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-offload-read">FSCTL_OFFLOAD_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_fsctl_offload_read_output">FSCTL_OFFLOAD_READ_OUTPUT</a>
 

 

