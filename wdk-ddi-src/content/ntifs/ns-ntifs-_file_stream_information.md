---
UID: NS:ntifs._FILE_STREAM_INFORMATION
title: FILE_STREAM_INFORMATION (ntifs.h)
description: Learn more about FILE_STREAM_INFORMATION structure.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FILE_STREAM_INFORMATION structure"]
ms.keywords: "*PFILE_STREAM_INFORMATION, FILE_STREAM_INFORMATION, FILE_STREAM_INFORMATION structure [Installable File System Drivers], PFILE_STREAM_INFORMATION, PFILE_STREAM_INFORMATION structure pointer [Installable File System Drivers], _FILE_STREAM_INFORMATION, fileinformationstructures_da535f6c-5769-4564-a2e7-e5a7ff952119.xml, ifsk.file_stream_information, ntifs/FILE_STREAM_INFORMATION, ntifs/PFILE_STREAM_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
req.typenames: FILE_STREAM_INFORMATION, *PFILE_STREAM_INFORMATION
f1_keywords:
 - _FILE_STREAM_INFORMATION
 - ntifs/_FILE_STREAM_INFORMATION
 - PFILE_STREAM_INFORMATION
 - ntifs/PFILE_STREAM_INFORMATION
 - FILE_STREAM_INFORMATION
 - ntifs/FILE_STREAM_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_STREAM_INFORMATION
 - PFILE_STREAM_INFORMATION
 - FILE_STREAM_INFORMATION
---

# FILE_STREAM_INFORMATION structure

## -description

The **FILE_STREAM_INFORMATION** structure is used to enumerate the streams for a file.

## -struct-fields

### -field NextEntryOffset

The offset of the next FILE_STREAM_INFORMATION entry. This member is zero if no other entries follow this one.

### -field StreamNameLength

Length, in bytes, of the **StreamName** string.

### -field StreamSize

Size, in bytes, of the stream.

### -field StreamAllocationSize

File stream allocation size, in bytes. Usually this value is a multiple of the sector or cluster size of the underlying physical device.

### -field StreamName

Unicode string that contains the name of the stream.

## -remarks

The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file. This operation can be performed in either of the following ways:

* By calling [**FltQueryInformationFile**](../fltkernel/nf-fltkernel-fltqueryinformationfile.md) or [**ZwQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md) and specifying FileStreamInformation for the **FileInformationClass** parameter. On return, the **FileInformation** buffer contains a FILE_STREAM_INFORMATION structure for each file stream.

* By sending an IRP_MJ_QUERY_INFORMATION request to the file system and specifying FileStreamInformation for the **FileInformationClass** parameter. On return, **Irp->AssociatedIrp.SystemBuffer** contains a FILE_STREAM_INFORMATION structure for each file stream.

No specific access rights are required to query this information. Thus this information is available as long as the file is open.

Support for stream enumeration is file system-dependent. If a file system does not support stream enumeration, it should return STATUS_INVALID_PARAMETER or STATUS_NOT_IMPLEMENTED for these requests.

If a file system supports stream enumeration, but the file has no streams other than the default data stream, which is unnamed, the file system should return a single FILE_STREAM_INFORMATION structure containing either "::$DATA" or a zero-length Unicode string as the **StreamName**.

NTFS returns "::$DATA" as the **StreamName** for the default data stream.

For a named data stream, NTFS appends ":$DATA" to the stream name. For example, for a user data stream with the name "Authors," NTFS returns ":Authors:$DATA" as the **StreamName**.

When calling a routine such as [**ZwCreateFile**](nf-ntifs-ntcreatefile.md) to open a named file stream, the ":$DATA" portion of the name can be omitted. For example, to open the "Authors" stream of a file named "Book," the caller can specify "Book:Authors" or "Book:Authors:$DATA" as the stream name. Both names are equivalent.

The size of the buffer passed in the **FileInformation** parameter to [**FltQueryInformationFile**](../fltkernel/nf-fltkernel-fltqueryinformationfile.md) or [**ZwQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md) must be at least **sizeof** (FILE_STREAM_INFORMATION). If this buffer is not large enough to hold a FILE_STREAM_INFORMATION structure for each file stream, **FltQueryInformationFile** or **ZwQueryInformationFile** returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. Because such an unsuccessful call to **FltQueryInformationFile** or **ZwQueryInformationFile** does not return the required buffer size, filter drivers must make one or more additional calls to **FltQueryInformationFile** or **ZwQueryInformationFile**, passing a larger buffer in each call, until the buffer is large enough.

Support for named data streams is file-system-specific. File system filter drivers can determine whether a file system supports named streams in either of the following ways:

* By calling [**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md) or [**ZwQueryVolumeInformationFile**](nf-ntifs-zwqueryvolumeinformationfile.md) and specifying FileFsAttributeInformation for the **FsInformationClass** parameter. On return, the **FsInformation** buffer contains a FILE_FS_ATTRIBUTE_INFORMATION structure. If the FILE_NAMED_STREAMS bit is set in the **FileSystemAttributes** member of this structure, the file system supports named streams.

* By sending an IRP_MJ_QUERY_VOLUME_INFORMATION request to the file system and specifying FileFsAttributeInformation for the **FsInformationClass** parameter. On return, **Irp->AssociatedIrp.SystemBuffer** contains a FILE_FS_ATTRIBUTE_INFORMATION structure. If the FILE_NAMED_STREAMS bit is set in the **FileSystemAttributes** member of this structure, the file system supports named streams.

The FILE_STREAM_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the **NextEntryOffset** value in each entry, except the last, falls on an 8-byte boundary.

## -see-also

[**FltQueryInformationFile**](../fltkernel/nf-fltkernel-fltqueryinformationfile.md)

[**FltQueryVolumeInformation**](/fltkernel/nf-fltkernel-fltqueryvolumeinformation.md)

[**IRP_MJ_QUERY_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-information)

[**IRP_MJ_QUERY_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-volume-information)

[**ZwCreateFile**](nf-ntifs-ntcreatefile.md)

[**ZwQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)

[**ZwQueryVolumeInformationFile**](nf-ntifs-zwqueryvolumeinformationfile.md)
