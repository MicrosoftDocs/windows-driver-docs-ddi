---
UID: NF:ntifs.NtFsControlFile
title: NtFsControlFile function (ntifs.h)
description: Learn more about the NtFsControlFile routine.
tech.root: kernel
ms.date: 01/07/2025
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NtFsControlFile
 - ntifs/NtFsControlFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtFsControlFile
---

# NtFsControlFile function

## -description

The **NtFsControlFile** routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.

## -parameters

### -param FileHandle [in]

Handle returned by [**NtCreateFile**](nf-ntifs-ntcreatefile.md) or [**NtOpenFile**](nf-ntifs-ntopenfile.md) for the file object representing the file or directory on which the specified action is to be performed. The file object must have been opened for asynchronous I/O if the caller specifies an **Event**, **ApcRoutine**, and an APC context (in **ApcContext**), or a completion context (in **ApcContext**).

### -param Event [in, optional]

Handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the Signaled state. This parameter is optional and can be NULL. It must be NULL if the caller will wait for the **FileHandle** to be set to the Signaled state.

### -param ApcRoutine [in, optional]

Address of a caller-supplied APC routine to be called when the requested operation completes. This parameter is optional and can be NULL. It must be NULL if there is an I/O completion object associated with the file object.

### -param ApcContext [in, optional]

Pointer to a caller-determined context area. This parameter value is used as the APC context if the caller supplies an APC, or is used as the completion context if an I/O completion object has been associated with the file object. When the operation completes, either the APC context is passed to the APC, if one was specified, or the completion context is included as part of the completion message that the I/O Manager posts to the associated I/O completion object.

This parameter is optional and can be NULL. It must be NULL if **ApcRoutine** is NULL and there is no I/O completion object associated with the file object.

### -param IoStatusBlock [out]

Pointer to an IO_STATUS_BLOCK structure that receives the final completion status and information about the operation. For successful calls that return data, the number of bytes written to the **OutputBuffer** is returned in the **Information** member of this structure.

### -param FsControlCode [in]

FSCTL_*XXX* code that indicates which file system control operation is to be carried out. The value of this parameter determines the formats and required lengths of the **InputBuffer** and **OutputBuffer**, as well as which of the following parameter pairs are required. For detailed information about the system-defined FSCTL_*XXX* codes, see the "Remarks" section of the reference entry for [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol).

### -param InputBuffer [in, optional]

Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target driver. If **FsControlCode** specifies an operation that doesn't require input data, this pointer is optional and can be NULL.

### -param InputBufferLength [in]

Size, in bytes, of the buffer at **InputBuffer**. This value is ignored if **InputBuffer** is NULL.

### -param OutputBuffer [out, optional]

Pointer to a caller-allocated output buffer in which information is returned from the target driver. If **FsControlCode** specifies an operation that doesn't produce output data, this pointer is optional and can be NULL.

### -param OutputBufferLength [in]

Size, in bytes, of the buffer at **OutputBuffer**. This value is ignored if **OutputBuffer** is NULL.

## -returns

**NtFsControlFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

## -remarks

**NtFsControlFile** provides a consistent view of the input and output data to the system and to kernel-mode drivers, while providing applications and underlying drivers with a driver-dependent method of specifying a communications interface.

If the caller opened the file for asynchronous I/O (with neither FILE_SYNCHRONOUS_*XXX* create/open option set), the specified event, if any, will be set to the signaled state when the device control operation completes. Otherwise, the file object specified by **FileHandle** will be set to the signaled state. If an **ApcRoutine** was specified, it is called with the **ApcContext** and **IoStatusBlock** pointers.

The following are some of the FSCTL codes documented for kernel-mode drivers:

* [**FSCTL_DELETE_REPARSE_POINT**](/windows-hardware/drivers/ifs/fsctl-delete-reparse-point)
* [**FSCTL_GET_REPARSE_POINT**](/windows-hardware/drivers/ifs/fsctl-get-reparse-point)
* [**FSCTL_OPBATCH_ACK_CLOSE_PENDING**](/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending)
* [**FSCTL_OPLOCK_BREAK_ACK_NO_2**](/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2)
* [**FSCTL_OPLOCK_BREAK_ACKNOWLEDGE**](/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge)
* [**FSCTL_OPLOCK_BREAK_NOTIFY**](/windows-hardware/drivers/ifs/fsctl-oplock-break-notify)
* [**FSCTL_REQUEST_BATCH_OPLOCK**](/windows-hardware/drivers/ifs/fsctl-request-batch-oplock)
* [**FSCTL_REQUEST_FILTER_OPLOCK**](/windows-hardware/drivers/ifs/fsctl-request-filter-oplock)
* [**FSCTL_REQUEST_OPLOCK_LEVEL_1**](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1)
* [**FSCTL_REQUEST_OPLOCK_LEVEL_2**](/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2)
* [**FSCTL_SET_REPARSE_POINT**](/windows-hardware/drivers/ifs/fsctl-set-reparse-point)

For more information about system-defined FSCTL_*XXX* codes, see the "Remarks" section of [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol), which is typically used by user-mode applications.

For more information about system-defined IOCTL_*XXX* codes, and about defining driver-specific IOCTL_*XXX* or FSCTL_*XXX* values, see [Using I/O Control Codes](/windows-hardware/drivers/kernel/using-i-o-control-codes) and [Device Input and Output Control Codes](/windows/win32/devio/device-input-and-output-control-ioctl-).

Minifilters should use [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) instead of **NtFsControlFile**.

Callers of **NtFsControlFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

If the call to the **NtFsControlFile** function occurs in user mode, you should use the name "**NtFsControlFile**" instead of "**ZwFsControlFile**".

For calls from kernel-mode drivers, the **Nt*XXX*** and **Zw*XXX*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*XXX*** and **Zw*XXX*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[**IRP_MJ_FILE_SYSTEM_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-file-system-control)

[**IoGetFunctionCodeFromCtlCode**](../wdm/nf-wdm-iogetfunctioncodefromctlcode.md)

[**IoIsOperationSynchronous**](nf-ntifs-ioisoperationsynchronous.md)

[**ZwClose**](nf-ntifs-ntclose.md)

[**ZwCreateFile**](nf-ntifs-ntcreatefile.md)

[**ZwDeviceIoControlFile**](nf-ntifs-zwdeviceiocontrolfile.md)

[**ZwOpenFile**](nf-ntifs-ntopenfile.md)
