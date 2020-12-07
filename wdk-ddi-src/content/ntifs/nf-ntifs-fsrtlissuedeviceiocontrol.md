---
UID: NF:ntifs.FsRtlIssueDeviceIoControl
title: FsRtlIssueDeviceIoControl function (ntifs.h)
description: The FsRtlIssueDeviceIoControl routine sends a synchronous device I/O control request to a target device object.
old-location: ifsk\fsrtlissuedeviceiocontrol.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIssueDeviceIoControl function"]
ms.keywords: FsRtlIssueDeviceIoControl, FsRtlIssueDeviceIoControl routine [Installable File System Drivers], ifsk.fsrtlissuedeviceiocontrol, ntifs/FsRtlIssueDeviceIoControl
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlIssueDeviceIoControl
 - ntifs/FsRtlIssueDeviceIoControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - FsRtlIssueDeviceIoControl
---

# FsRtlIssueDeviceIoControl function


## -description

The <b>FsRtlIssueDeviceIoControl</b> routine sends a synchronous device I/O control request to a target device object.

## -parameters

### -param DeviceObject 

[in]
The target device object.

### -param IoCtl 

[in]
The IOCTL control code to issue.

### -param Flags

<p>The desired IRP flags to set for IOCTL request.</p>

### -param InputBuffer 

[in, optional]
An optional buffer containing the input data for the request.

### -param InputBufferLength 

[in]
The length, in bytes, of the input data in <i>InputBuffer</i>.

### -param OutputBuffer 

[out, optional]
An optional caller-supplied output buffer for returned data.

### -param OutputBufferLength 

[in]
The length, in bytes, of the output data buffer at <i>OutputBuffer</i>.

### -param IosbInformation 

[in]
A pointer to a <b>ULONG</b> status value to receive the information field value set in the I/O status block at completion of the request.

## -returns

<b>FsRtlIssueDeviceIoControl</b> returns <b>STATUS_SUCCESS</b> or an another <b>NTSTATUS</b> value returned in the status block from the I/O operation.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeviceiocontrolfile">FltDeviceIoControlFile</a>
