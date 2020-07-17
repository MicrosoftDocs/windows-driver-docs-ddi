---
UID: NF:ntifs.NtFlushBuffersFileEx
title: NtFlushBuffersFileEx function (ntifs.h)
description: The NtFlushBuffersFileEx routine is called by a file system legacy filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.
old-location: kernel\zwflushbuffersfileex.htm
tech.root: kernel
ms.assetid: C081CCF5-D13C-405C-A430-31805A16724A
ms.date: 01/02/2020
keywords: ["NtFlushBuffersFileEx function"]
ms.keywords: FLUSH_FLAGS_FILE_DATA_ONLY, FLUSH_FLAGS_NO_SYNC, NtFlushBuffersFileEx, ZwFlushBuffersFileEx, ZwFlushBuffersFileEx routine [Kernel-Mode Driver Architecture], kernel.zwflushbuffersfileex, ntifs/NtFlushBuffersFileEx, ntifs/ZwFlushBuffersFileEx
f1_keywords:
 - "ntifs/NtFlushBuffersFileEx"
 - "NtFlushBuffersFileEx"
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
- ZwFlushBuffersFileEx
- NtFlushBuffersFileEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtFlushBuffersFileEx function

## -description

The **NtFlushBuffersFileEx** routine is called by a file system legacy filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.

## -parameters

### -param FileHandle [in]

Handle returned by [**NtCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile) or [**NtOpenFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile) for the file whose buffers will be flushed. This parameter is required and cannot be NULL.

### -param Flags [in]

Flush operation flags. *Flags* can be 0 or one of the following values *if the file is on an NTFS file system*.

| Value | Meaning |
| ----- | ------- |
| FLUSH_FLAGS_FILE_DATA_ONLY | File data in the file cache will be written. No metadata is written and the underlying storage is not synchronized to flush its cache. This flag is not valid with volume handles. |
| FLUSH_FLAGS_NO_SYNC | File data and metadata in the file cache will be written. The underlying storage is not synchronized to flush its cache. This flag is not valid with volume handles. |
| FLUSH_FLAGS_FILE_DATA_SYNC_ONLY | Data from the given file will be written from the Windows in-memory cache. Timestamp updating will be skipped as much as possible. The underlying storage is synchronized to flush its cache. This flag is not valid with volume or directory handles. |

### -param Parameters

Pointer to a block with additional parameters. This parameter must currently be set to NULL.

### -param ParametersSize

The size, in bytes, of the block that *Parameters* point to. This parameter must currently be set to 0.

### -param IoStatusBlock [out]

Address of the caller's I/O status block. This parameter is required and cannot be NULL.

## -returns

**NtFlushBuffersFileEx** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_MEDIA_WRITE_PROTECTED | The file resides on a write-protected volume; this is an error code. |
| STATUS_VOLUME_DISMOUNTED | The file resides on a volume that is not currently mounted; this is an error code. |
| STATUS_ACCESS_DENIED | The file does has neither write or append access. |

## -remarks

Minifilter drivers should call [**FltFlushBuffers2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltflushbuffers2) instead of calling **NtFlushBuffersFileEx**.

A legacy file system filter driver can call **NtFlushBuffersFileEx** to issue an [IRP_MJ_FLUSH_BUFFERS](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers) request to the file system for a given file. The flush operation is synchronous.

Callers of **NtFlushBuffersFileEx** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs).

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FltFlushBuffers2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltflushbuffers2)

[IRP_MJ_FLUSH_BUFFERS](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers)

[Using Nt and Zw Versions of the Native System Services Routines](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile)

[**NtOpenFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile)
