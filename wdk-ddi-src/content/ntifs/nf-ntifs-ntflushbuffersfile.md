---
UID: NF:ntifs.NtFlushBuffersFile
title: NtFlushBuffersFile function (ntifs.h)
description: The NtFlushBuffersFile routine is called by a file system legacy filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.
old-location: kernel\ZwFlushBuffersFile.htm
tech.root: kernel
ms.date: 11/26/2019
keywords: ["NtFlushBuffersFile function"]
ms.keywords: FLUSH_FLAGS_FILE_DATA_ONLY, FLUSH_FLAGS_NO_SYNC, NtFlushBuffersFile, ZwFlushBuffersFile, ZwFlushBuffersFile routine [Kernel-Mode Driver Architecture], kernel.ZwFlushBuffersFile, ntifs/NtFlushBuffersFile, ntifs/ZwFlushBuffersFile
f1_keywords:
 - "ntifs/NtFlushBuffersFile"
 - "NtFlushBuffersFile"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (See Remarks section.)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwFlushBuffersFile
- NtFlushBuffersFile
targetos: Windows
req.typenames: 
---

# NtFlushBuffersFile function

## -description

The **NtFlushBuffersFile** routine is called by a file system legacy filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.

## -parameters

### -param FileHandle 
[in]
Handle returned by [**NtCreateFile**](./nf-ntifs-ntcreatefile.md) or [**NtOpenFile**](./nf-ntifs-ntopenfile.md) for the file whose buffers will be flushed. This parameter is required and cannot be NULL.

### -param IoStatusBlock 
[out]
Address of the caller's I/O status block. This parameter is required and cannot be NULL.

## -returns

**NtFlushBuffersFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_MEDIA_WRITE_PROTECTED | The file resides on a write-protected volume; this is an error code. |
| STATUS_VOLUME_DISMOUNTED | The file resides on a volume that is not currently mounted; this is an error code. |
| STATUS_ACCESS_DENIED | The file does has neither write or append access. |

## -remarks

Minifilter drivers should call [**FltFlushBuffers**](../fltkernel/nf-fltkernel-fltflushbuffers.md) instead of calling **NtFlushBuffersFile**.

A legacy file system filter driver can call **NtFlushBuffersFile** to issue an [IRP_MJ_FLUSH_BUFFERS](/windows-hardware/drivers/ifs/irp-mj-flush-buffers) request to the file system for a given file. The flush operation is synchronous.

Callers of **NtFlushBuffersFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FltFlushBuffers**](../fltkernel/nf-fltkernel-fltflushbuffers.md)

[IRP_MJ_FLUSH_BUFFERS](/windows-hardware/drivers/ifs/irp-mj-flush-buffers)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtCreateFile**](./nf-ntifs-ntcreatefile.md)

[**NtOpenFile**](./nf-ntifs-ntopenfile.md)
