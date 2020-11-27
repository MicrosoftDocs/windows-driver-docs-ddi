---
UID: NF:fltkernel.FltFsControlFile
title: FltFsControlFile function (fltkernel.h)
description: The FltFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.
old-location: ifsk\fltfscontrolfile.htm
tech.root: ifsk
ms.assetid: afc72cdf-ea29-4e78-95a0-fc621e3290a7
ms.date: 04/16/2018
keywords: ["FltFsControlFile function"]
ms.keywords: FltApiRef_e_to_o_3cad833f-9ece-410a-896d-1b3fe897c251.xml, FltFsControlFile, FltFsControlFile routine [Installable File System Drivers], fltkernel/FltFsControlFile, ifsk.fltfscontrolfile
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFsControlFile
 - fltkernel/FltFsControlFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltFsControlFile
---

# FltFsControlFile function


## -description

The <b>FltFsControlFile</b> routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in]
File object pointer for the file or directory that is the target of this request. This parameter is required and cannot be <b>NULL</b>.

### -param FsControlCode 

[in]
FSCTL_<i>XXX</i> code that indicates which file system operation is to be carried out. The value of this parameter determines the formats and required lengths of the <i>InputBuffer</i> and <i>OutputBuffer</i>, and it determines which of the following parameter pairs (<i>InputBuffer</i> and <i>InputBufferLength</i>, <i>OutputBuffer</i> and <i>OutputBufferLength</i>) is required.

### -param InputBuffer 

[in, optional]
Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target driver. If the <i>FsControlCode</i> parameter specifies an operation that does not require input data, this parameter is optional and can be <b>NULL</b>.

### -param InputBufferLength 

[in]
Size, in bytes, of the buffer at <i>InputBuffer</i>. This value is ignored if <i>InputBuffer</i> is <b>NULL</b>.

### -param OutputBuffer 

[out, optional]
Pointer to a caller-allocated output buffer in which information is returned from the target driver. If the <i>FsControlCode</i> parameter specifies an operation that does not require output data, this parameter is optional and can be <b>NULL</b>.

### -param OutputBufferLength 

[in]
Size, in bytes, of the buffer at <i>OutputBuffer</i>. This value is ignored if <i>OutputBuffer</i> is <b>NULL</b>.

### -param LengthReturned 

[out, optional]
Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the buffer at <i>OutputBuffer</i>. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>FltFsControlFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value.

## -remarks

Minifilter drivers should call this routine instead of <a href="/en-us/windows-hardware/drivers/ddi/ntifs/nf-ntifs-zwfscontrolfile">ZwFsControlFile</a>.

The following FSCTL codes are currently documented for kernel-mode drivers: 


<a href="/windows-hardware/drivers/ifs/fsctl-delete-reparse-point">FSCTL_DELETE_REPARSE_POINT</a>



<a href="/windows-hardware/drivers/ifs/fsctl-get-reparse-point">FSCTL_GET_REPARSE_POINT</a>



<a href="/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-set-reparse-point">FSCTL_SET_REPARSE_POINT</a>


For more information about the system-defined FSCTL_<i>XXX</i> codes, see the Remarks section of the reference entry for DeviceIoControl in the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeviceiocontrolfile">FltDeviceIoControlFile</a>



<a href="/en-us/windows-hardware/drivers/ddi/ntifs/nf-ntifs-zwfscontrolfile">ZwFsControlFile</a>