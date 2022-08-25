---
UID: NS:wdm._SECTION_OBJECT_POINTERS
title: _SECTION_OBJECT_POINTERS (wdm.h)
description: The SECTION_OBJECT_POINTERS structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream.
old-location: kernel\section_object_pointers.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["SECTION_OBJECT_POINTERS structure"]
ms.keywords: "*PSECTION_OBJECT_POINTERS, PSECTION_OBJECT_POINTERS, PSECTION_OBJECT_POINTERS structure pointer [Kernel-Mode Driver Architecture], SECTION_OBJECT_POINTERS, SECTION_OBJECT_POINTERS structure [Kernel-Mode Driver Architecture], _SECTION_OBJECT_POINTERS, kernel.section_object_pointers, kstruct_d_2b10d7da-97f5-43d6-8f46-0d8ee393ed84.xml, wdm/PSECTION_OBJECT_POINTERS, wdm/SECTION_OBJECT_POINTERS"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available in all versions of Windows that Microsoft supports.
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
req.typenames: SECTION_OBJECT_POINTERS
f1_keywords:
 - _SECTION_OBJECT_POINTERS
 - wdm/_SECTION_OBJECT_POINTERS
 - SECTION_OBJECT_POINTERS
 - wdm/SECTION_OBJECT_POINTERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _SECTION_OBJECT_POINTERS
 - SECTION_OBJECT_POINTERS
---

# _SECTION_OBJECT_POINTERS structure


## -description

The <b>SECTION_OBJECT_POINTERS</b> structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream.

## -struct-fields

### -field DataSectionObject

Opaque pointer to a data section object (that is, a <b>CONTROL_AREA</b> structure) that is used to track state information for a data file stream. Memory manager sets this member when the operating system first caches the data stream. A <b>NULL</b> value indicates that the data stream is <u>currently</u> not in memory; this value, however, can change at any time.

### -field SharedCacheMap

Opaque pointer to a cache map object (that is, a <b>SHARED_CACHE_MAP</b> structure) that is used to track views that are mapped to the data file stream. Cache manager sets this member when the operating system first caches the stream. A <b>NULL</b> value indicates that the data stream is <u>currently</u> not cached; this value, however, can change at any time.

### -field ImageSectionObject

Opaque pointer to an image section object (that is, a <b>CONTROL_AREA</b> structure) that is used to track state information for an executable file stream. Memory manager sets this member whenever an executable image section is created for the stream. A <b>NULL</b> value indicates that the executable image is <u>currently</u> not in memory; this value, however, can change at any time.

## -remarks

The <b>SECTION_OBJECT_POINTERS</b> structure links a file object to a file stream's section object. That is, through its members, the <b>SECTION_OBJECT_POINTERS</b> structure connects a particular file object to virtual memory control structures that keep track of the stream's contents when they are in memory, and allow the operating system to fetch those contents when they are not. 

There is a one-to-one relationship between a <b>SECTION_OBJECT_POINTERS</b> structure and a file stream. Multiple file objects can be associated with a particular file stream, each representing an open instance of the stream. However, only one <b>SECTION_OBJECT_POINTERS</b> structure can be associated with a given stream. If there are multiple file objects for a stream, the <b>SectionObjectPointer</b> member for all file objects must point to the same <b>SECTION_OBJECT_POINTERS</b> structure (that is associated with the stream).

For the <u>first</u> file stream open request, the file system or the redirector driver must:

<ol>
<li>
Allocate a <b>SECTION_OBJECT_POINTERS</b> structure from a nonpaged pool.

</li>
<li>
Initialize all members of the allocated <b>SECTION_OBJECT_POINTERS</b> structure to <b>NULL</b>.

</li>
<li>
  Set the <b>SectionObjectPointer</b> member of the associate file object to point to the initialized <b>SECTION_OBJECT_POINTERS</b> structure.

</li>
</ol>
For <u>subsequent</u> open requests to the <u>same</u> file stream, the file system or the redirector driver must set the <b>SectionObjectPointer</b> member of the associated file object to point to the previously allocated <b>SECTION_OBJECT_POINTERS</b> structure for the file stream.

<div class="alert"><b>Warning</b>    File system filter drivers must treat the members of the <b>SECTION_OBJECT_POINTERS</b> structure as opaque because the underlying file system is responsible for the synchronization of the members and, therefore, could change their values at any time.</div>
<div> </div>
<div class="alert"><b>Note</b>    A file is composed of one or more streams, depending on the file system. For more information, see <a href="/windows-hardware/drivers/ifs/file-streams--stream-contexts--and-per-stream-contexts">File Streams, Stream Contexts, and Per-Stream Contexts</a>.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="/windows-hardware/drivers/ifs/the-fobx-structure">FOBX</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-mmflushimagesection">MmFlushImageSection</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>

