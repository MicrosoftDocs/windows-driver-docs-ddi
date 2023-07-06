---
UID: NF:ntifs.NtWriteFile
title: NtWriteFile function (ntifs.h)
description: Learn more about the NtWriteFile routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["NtWriteFile function"]
ms.keywords: NtWriteFile, ZwWriteFile, ZwWriteFile routine [Kernel-Mode Driver Architecture], k111_97437555-3cb5-497b-8ebb-c683771da9f4.xml, kernel.zwwritefile, wdm/NtWriteFile, wdm/ZwWriteFile
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - NtWriteFile
 - ntifs/NtWriteFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtWriteFile
---

# NtWriteFile function

## -description

The **ZwWriteFile** routine writes data to an open file.

## -parameters

### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to [**NtCreateFile**](nf-ntifs-ntcreatefile.md) or [**NtOpenFile**](nf-ntifs-ntopenfile.md).

### -param Event [in, optional]

Optionally, a handle to an event object to set to the signaled state after the write operation completes. Device and intermediate drivers should set this parameter to NULL.

### -param ApcRoutine [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to NULL.

### -param ApcContext [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to NULL.

### -param IoStatusBlock [out]

Pointer to an [IO_STATUS_BLOCK](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the requested write operation. The **Information** member receives the number of bytes actually written to the file.

### -param Buffer [in]

Pointer to a caller-allocated buffer that contains the data to write to the file.

### -param Length [in]

The size, in bytes, of the buffer pointed to by **Buffer**.

### -param ByteOffset [in, optional]

Pointer to a variable that specifies the starting byte offset in the file for beginning the write operation. If **Length** and **ByteOffset** specify a write operation past the current end-of-file mark, **NtWriteFile** automatically extends the file and updates the end-of-file mark; any bytes that are not explicitly written between such old and new end-of-file marks are defined to be zero.

If the call to [**NtCreateFile**](nf-ntifs-ntcreatefile.md) set only the **DesiredAccess** flag FILE_APPEND_DATA, **ByteOffset** is ignored. Data in the given **Buffer**, for **Length** bytes, is written starting at the current end of file.

If the call to [**NtCreateFile**](nf-ntifs-ntcreatefile.md) set either of the **CreateOptions** flags, FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT, the I/O Manager maintains the current file position. If so, the caller of **NtWriteFile** can specify that the current file position offset be used instead of an explicit **ByteOffset** value. This specification can be made by using one of the following methods:

* *Specify a pointer to a LARGE_INTEGER value with the **HighPart** member set to -1 and the **LowPart** member set to the system-defined value FILE_USE_FILE_POINTER_POSITION.
* Pass a NULL pointer for **ByteOffset**.

**NtWriteFile** updates the current file position by adding the number of bytes written when it completes the write operation, if it is using the current file position maintained by the I/O Manager.

Even when the I/O Manager is maintaining the current file position, the caller can reset this position by passing an explicit **ByteOffset** value to **NtWriteFile**. Doing this automatically changes the current file position to that **ByteOffset**value, performs the write operation, and then updates the position according to the number of bytes actually written. This technique gives the caller atomic seek-and-write service.

It is also possible to cause a write operation to start at the current end of file by specifying for **ByteOffset** a pointer to a LARGE_INTEGER value with **HighPart** set to -1 and **LowPart** set to FILE_WRITE_TO_END_OF_FILE. This works regardless of whether the I/O Manager is maintaining the current file position.

### -param Key [in, optional]

Device and intermediate drivers should set this pointer to NULL.

## -returns

**NtWriteFile** returns STATUS_SUCCESS on success or the appropriate NTSTATUS error code on failure.

## -remarks

Callers of **NtWriteFile** must have already called [**NtCreateFile**](nf-ntifs-ntcreatefile.md) with the FILE_WRITE_DATA, FILE_APPEND_DATA, or GENERIC_WRITE flag set in the **DesiredAccess** parameter. Note that having only FILE_APPEND_DATA access to a file does not allow the caller to write anywhere in the file except at the current end-of-file mark, while having FILE_WRITE_DATA access to a file does not preclude the caller from writing to or beyond the end of a file.

If the preceding call to [**NtCreateFile**](nf-ntifs-ntcreatefile.md) set the **CreateOptions** flag FILE_NO_INTERMEDIATE_BUFFERING, the **Length** and **ByteOffset** parameters to **NtWriteFile** must be an integral of the sector size. For more information, see **NtCreateFile**.

**NtWriteFile** begins the write operation to the file at **ByteOffset**, at the current file position, or at the end-of-file mark. It terminates the write operation when it has written **Length** bytes from **Buffer**. If necessary, it extends the length of the file and resets the end-of-file mark.

If the caller opened the file with the **DesiredAccess** SYNCHRONIZE flag set, the caller can wait for this routine to set the given **FileHandle** to the signaled state.

Drivers should call **NtWriteFile** in the context of the system process in three cases:

* The driver creates the file handle that it passes to **NtWriteFile**.
* **NtWriteFile** notifies the driver of I/O completion by means of an event created by the driver.
* **NtWriteFile** notifies the driver of I/O completion by means of an APC callback routine that the driver passes to **NtWriteFile**.

File and event handles are only valid in the process context where the handles are created. Therefore, to avoid security holes, the driver should create any file or event handle that it passes to **NtWriteFile** in the context of the system process instead of the process context that the driver is in.

Likewise, **NtWriteFile** should be called in the context of the system process if it notifies the driver of I/O completion by means of an APC, because APCs are always fired in the context of the thread issuing the I/O request. If the driver calls **NtWriteFile** in the context of a process other than the system process, the APC could be delayed indefinitely, or it might not fire at all as the originating thread may never enter an alertable wait state.

For more information about working with files, see [Using Files in a Driver](/windows-hardware/drivers/kernel/using-files-in-a-driver).

Callers of **NtWriteFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

If the call to this function occurs in user mode, you should use the name "**NtWriteFile**" instead of "**ZwWriteFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**KeInitializeEvent**](../wdm/nf-wdm-keinitializeevent.md)

[**NtCreateFile**](nf-ntifs-ntcreatefile.md)

[**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)

[**NtReadFile**](nf-ntifs-ntreadfile.md)

[**NtSetInformationFile**](nf-ntifs-ntsetinformationfile.md)
