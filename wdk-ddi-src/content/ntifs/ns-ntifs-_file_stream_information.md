---
UID: NS:ntifs._FILE_STREAM_INFORMATION
title: _FILE_STREAM_INFORMATION (ntifs.h)
description: The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file.
old-location: ifsk\file_stream_information.htm
tech.root: ifsk
ms.assetid: 03472920-cb22-42e1-b0e5-488c0319fc03
ms.date: 04/16/2018
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
 - FILE_STREAM_INFORMATION
---

# _FILE_STREAM_INFORMATION structure


## -description

The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file.

## -struct-fields

### -field NextEntryOffset

The offset of the next FILE_STREAM_INFORMATION entry. This member is zero if no other entries follow this one.

### -field StreamNameLength

Length, in bytes, of the <b>StreamName</b> string.

### -field StreamSize

Size, in bytes, of the stream.

### -field StreamAllocationSize

File stream allocation size, in bytes. Usually this value is a multiple of the sector or cluster size of the underlying physical device.

### -field StreamName

Unicode string that contains the name of the stream.

## -remarks

The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file. This operation can be performed in either of the following ways: 

<ul>
<li>
By calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> and specifying FileStreamInformation for the <i>FileInformationClass</i> parameter. On return, the <i>FileInformation</i> buffer contains a FILE_STREAM_INFORMATION structure for each file stream. 

</li>
<li>
By sending an IRP_MJ_QUERY_INFORMATION request to the file system and specifying FileStreamInformation for the <i>FileInformationClass</i> parameter. On return, <b>Irp->AssociatedIrp.SystemBuffer</b> contains a FILE_STREAM_INFORMATION structure for each file stream. 

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as the file is open. 

Support for stream enumeration is file system-dependent. If a file system does not support stream enumeration, it should return STATUS_INVALID_PARAMETER or STATUS_NOT_IMPLEMENTED for these requests. 

If a file system supports stream enumeration, but the file has no streams other than the default data stream, which is unnamed, the file system should return a single FILE_STREAM_INFORMATION structure containing either "::$DATA" or a zero-length Unicode string as the <b>StreamName</b>. 

NTFS returns "::$DATA" as the <b>StreamName</b> for the default data stream. 

For a named data stream, NTFS appends ":$DATA" to the stream name. For example, for a user data stream with the name "Authors," NTFS returns ":Authors:$DATA" as the <b>StreamName</b>. 

When calling a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> to open a named file stream, the ":$DATA" portion of the name can be omitted. For example, to open the "Authors" stream of a file named "Book," the caller can specify "Book:Authors" or "Book:Authors:$DATA" as the stream name. Both names are equivalent. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> must be at least <b>sizeof</b> (FILE_STREAM_INFORMATION). If this buffer is not large enough to hold a FILE_STREAM_INFORMATION structure for each file stream, <b>FltQueryInformationFile</b> or <b>ZwQueryInformationFile</b> returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. Because such an unsuccessful call to <b>FltQueryInformationFile</b> or <b>ZwQueryInformationFile</b> does not return the required buffer size, filter drivers must make one or more additional calls to <b>FltQueryInformationFile</b> or <b>ZwQueryInformationFile</b>, passing a larger buffer in each call, until the buffer is large enough. 

Support for named data streams is file-system-specific. File system filter drivers can determine whether a file system supports named streams in either of the following ways: 

<ul>
<li>
By calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a> and specifying FileFsAttributeInformation for the <i>FsInformationClass</i> parameter. On return, the <i>FsInformation</i> buffer contains a FILE_FS_ATTRIBUTE_INFORMATION structure. If the FILE_NAMED_STREAMS bit is set in the <b>FileSystemAttributes</b> member of this structure, the file system supports named streams. 

</li>
<li>
By sending an IRP_MJ_QUERY_VOLUME_INFORMATION request to the file system and specifying FileFsAttributeInformation for the <i>FsInformationClass</i> parameter. On return, <b>Irp->AssociatedIrp.SystemBuffer</b> contains a FILE_FS_ATTRIBUTE_INFORMATION structure. If the FILE_NAMED_STREAMS bit is set in the <b>FileSystemAttributes</b> member of this structure, the file system supports named streams. 

</li>
</ul>
The FILE_STREAM_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>

