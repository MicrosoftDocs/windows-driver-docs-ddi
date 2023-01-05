---
UID: NS:wdm._SECTION_OBJECT_POINTERS
title: SECTION_OBJECT_POINTERS (wdm.h)
description: The SECTION_OBJECT_POINTERS structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream.
tech.root: kernel
ms.date: 12/16/2022
keywords: ["SECTION_OBJECT_POINTERS structure"]
ms.keywords: "*PSECTION_OBJECT_POINTERS, PSECTION_OBJECT_POINTERS, PSECTION_OBJECT_POINTERS structure pointer [Kernel-Mode Driver Architecture], SECTION_OBJECT_POINTERS, SECTION_OBJECT_POINTERS structure [Kernel-Mode Driver Architecture], _SECTION_OBJECT_POINTERS, kernel.section_object_pointers, kstruct_d_2b10d7da-97f5-43d6-8f46-0d8ee393ed84.xml, wdm/PSECTION_OBJECT_POINTERS, wdm/SECTION_OBJECT_POINTERS"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
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

## -description

The **SECTION_OBJECT_POINTERS** structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream.

## -struct-fields

### -field DataSectionObject

Opaque pointer to a data section object (that is, a **CONTROL_AREA** structure) that is used to track state information for a data file stream. Memory manager sets this member when the operating system first caches the data stream. A **NULL** value indicates that the data stream is currently not in memory; this value, however, can change at any time.

### -field SharedCacheMap

Opaque pointer to a cache map object (that is, a **SHARED_CACHE_MAP** structure) that is used to track views that are mapped to the data file stream. Cache manager sets this member when the operating system first caches the stream. A **NULL** value indicates that the data stream is currently not cached; this value, however, can change at any time.

### -field ImageSectionObject

Opaque pointer to an image section object (that is, a **CONTROL_AREA** structure) that is used to track state information for an executable file stream. Memory manager sets this member whenever an executable image section is created for the stream. A **NULL** value indicates that the executable image is currently not in memory; this value, however, can change at any time.

## -remarks

The **SECTION_OBJECT_POINTERS** structure links a file object to a file stream's section object. That is, through its members, the **SECTION_OBJECT_POINTERS** structure connects a particular file object to virtual memory control structures that keep track of the stream's contents when they are in memory, and allow the operating system to fetch those contents when they are not.

There is a one-to-one relationship between a **SECTION_OBJECT_POINTERS** structure and a file stream. Multiple file objects can be associated with a particular file stream, each representing an open instance of the stream. However, only one **SECTION_OBJECT_POINTERS** structure can be associated with a given stream. If there are multiple file objects for a stream, the **SectionObjectPointer** member for all file objects must point to the same **SECTION_OBJECT_POINTERS** structure (that is associated with the stream).

For the first file stream open request, the file system or the redirector driver must:

1. Allocate a **SECTION_OBJECT_POINTERS** structure from a nonpaged pool.

1. Initialize all members of the allocated **SECTION_OBJECT_POINTERS** structure to **NULL**.

1. Set the **SectionObjectPointer** member of the associate file object to point to the initialized **SECTION_OBJECT_POINTERS** structure.

For subsequent open requests to the same file stream, the file system or the redirector driver must set the **SectionObjectPointer** member of the associated file object to point to the previously allocated **SECTION_OBJECT_POINTERS** structure for the file stream.

> [!WARNING]
> File system filter drivers must treat the members of the **SECTION_OBJECT_POINTERS** structure as opaque because the underlying file system is responsible for the synchronization of the members and, therefore, could change their values at any time.

A file is composed of one or more streams, depending on the file system. For more information, see [File Streams, Stream Contexts, and Per-Stream Contexts](/windows-hardware/drivers/ifs/file-streams--stream-contexts--and-per-stream-contexts).

## -see-also

[CcInitializeCacheMap](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap)

[DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)

[FILE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object)

[FOBX](/windows-hardware/drivers/ifs/the-fobx-structure)

[FSRTL_ADVANCED_FCB_HEADER](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header)

[IoGetDeviceObjectPointer](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer)

[MmFlushImageSection](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-mmflushimagesection)

[ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject)
