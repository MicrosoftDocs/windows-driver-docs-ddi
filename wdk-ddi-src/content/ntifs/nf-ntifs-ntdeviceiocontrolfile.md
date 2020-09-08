---
UID: NF:ntifs.NtDeviceIoControlFile
title: NtDeviceIoControlFile function (ntifs.h)
description: The ZwDeviceIoControlFile routine sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified operation.
old-location: kernel\zwdeviceiocontrolfile.htm
tech.root: kernel
ms.assetid: 4dc38fcd-4b87-4c34-8ae2-685bf47e3fde
ms.date: 04/30/2018
keywords: ["NtDeviceIoControlFile function"]
ms.keywords: NtDeviceIoControlFile, ZwDeviceIoControlFile, ZwDeviceIoControlFile routine [Kernel-Mode Driver Architecture], k111_03e754fc-b6b5-4266-9be1-452d5ba5331c.xml, kernel.zwdeviceiocontrolfile, ntifs/NtDeviceIoControlFile, ntifs/ZwDeviceIoControlFile
req.header: ntifs.h
req.include-header: Ntifs.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
 - NtDeviceIoControlFile
 - ntifs/NtDeviceIoControlFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwDeviceIoControlFile
 - NtDeviceIoControlFile
---

# NtDeviceIoControlFile function


## -description

The <b>ZwDeviceIoControlFile</b> routine sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified operation.

## -parameters

### -param FileHandle 

[in]
Handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a> for the file object representing the device to which the control information should be given or from which information should be returned. The file object must have been opened for asynchronous I/O if the caller specifies an <i>Event</i>, <i>ApcRoutine</i>, and an APC context (in <i>ApcContext</i>), or a completion context (in <i>ApcContext</i>). For I/O to an underlying mass-storage device, the file object must have been opened for Direct Access to Storage Device (DASD) access.

### -param Event 

[in, optional]
Handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the Signaled state. This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if the caller will wait for the <i>FileHandle</i> to be set to the Signaled state.

### -param ApcRoutine 

[in, optional]
Address of an optional, caller-supplied APC routine to be called when the requested operation completes. This parameter can be <b>NULL</b>. It must be <b>NULL</b> if there is an I/O completion object associated with the file object.

### -param ApcContext 

[in, optional]
Pointer to a caller-determined context area. This parameter value is used as the APC context if the caller supplies an APC, or is used as the completion context if an I/O completion object has been associated with the file object. When the operation completes, either the APC context is passed to the APC, if one was specified, or the completion context is included as part of the completion message that the I/O Manager posts to the associated I/O completion object.

This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if <i>ApcRoutine</i> is <b>NULL</b> and there is no I/O completion object associated with the file object.

### -param IoStatusBlock 

[out]
Pointer to a variable that receives the final completion status and information about the operation. For successful calls that return data, the number of bytes written to the <i>OutputBuffer</i> is returned in the <b>Information</b> member.

### -param IoControlCode 

[in]
IOCTL_<i>XXX</i> code that indicates which device I/O control operation is to be carried out on, usually by the underlying device driver. The value of this parameter determines the format and required length of the <i>InputBuffer</i> and <i>OutputBuffer</i>, as well as which of the following parameter pairs are required. For detailed information about the system-defined, device-type-specific IOCTL_<i>XXX</i> codes, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/">device technology-specific section</a> of the Microsoft Windows Driver Kit (WDK) documentation and <a href="https://docs.microsoft.com/windows/desktop/DevIO/device-input-and-output-control-ioctl-">Device Input and Output Control Codes</a> in the Microsoft Windows SDK documentation.

### -param InputBuffer 

[in, optional]
Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target device. If <i>IoControlCode</i> specifies an operation that does not require input data, this pointer can be <b>NULL</b>.

### -param InputBufferLength 

[in]
Size, in bytes, of the buffer at <i>InputBuffer</i>. If <i>InputBuffer</i> is <b>NULL</b>, set <i>InputBufferLength</i> to zero.

### -param OutputBuffer 

[out, optional]
Pointer to a caller-allocated output buffer in which information is returned from the target device. If <i>IoControlCode</i> specifies an operation that does not produce output data, this pointer can be <b>NULL</b>.

### -param OutputBufferLength 

[in]
Size, in bytes, of the buffer at <i>OutputBuffer</i>. If <i>OutputBuffer</i> is <b>NULL</b>, set <i>OutputBufferLength</i> to zero.

## -returns

<b>ZwDeviceIoControlFile</b> returns STATUS_SUCCESS if the underlying driver(s) successfully carried out the requested operation. Otherwise, the return value can be an error status code propagated from an underlying driver. Possible error status codes include the following:

## -remarks

<b>ZwDeviceIoControlFile</b> provides a consistent view of the input and output data to the system and to kernel-mode drivers, while providing applications and underlying drivers with a device-dependent method of specifying a communications interface.

For more information about system-defined IOCTL_<i>XXX</i> codes, and about defining driver-specific IOCTL_<i>XXX</i> or FSCTL_<i>XXX</i> values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a> in the <i>Kernel Mode Architecture Guide</i> and <a href="https://docs.microsoft.com/windows/desktop/DevIO/device-input-and-output-control-ioctl-">Device Input and Output Control Codes</a> in the Microsoft Windows SDK documentation.

If the caller opened the file for asynchronous I/O (with neither FILE_SYNCHRONOUS_<i>XXX</i> create/open option set), the specified event, if any, will be set to the signaled state when the device control operation completes. Otherwise, the file object specified by <i>FileHandle</i> will be set to the signaled state. If an <i>ApcRoutine</i> was specified, it is called with the <i>ApcContext</i> and <i>IoStatusBlock</i> pointers.

Minifilters should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeviceiocontrolfile">FltDeviceIoControlFile</a> instead of <b>ZwDeviceIoControlFile</b>.

Callers of <b>ZwDeviceIoControlFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwDeviceIoControlFile</b> function occurs in user mode, you should use the name "<b>NtDeviceIoControlFile</b>" instead of "<b>ZwDeviceIoControlFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeviceiocontrolfile">FltDeviceIoControlFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a>

