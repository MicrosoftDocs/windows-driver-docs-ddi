---
UID: NS:ntifs._FSRTL_PER_FILEOBJECT_CONTEXT
title: FSRTL_PER_FILEOBJECT_CONTEXT (ntifs.h)
description: The opaque FSRTL_PER_FILEOBJECT_CONTEXT structure is used by the operating system to track file system filter-driver-defined context information structures for a file object.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FSRTL_PER_FILEOBJECT_CONTEXT structure"]
ms.keywords: "*PFSRTL_PER_FILEOBJECT_CONTEXT, FSRTL_PER_FILEOBJECT_CONTEXT, FSRTL_PER_FILEOBJECT_CONTEXT structure [Installable File System Drivers], PFSRTL_PER_FILEOBJECT_CONTEXT, PFSRTL_PER_FILEOBJECT_CONTEXT structure pointer [Installable File System Drivers], _FSRTL_PER_FILEOBJECT_CONTEXT, contextstructures_0b5fadaf-8b73-4a63-9e1d-fa08359d5e8d.xml, ifsk.fsrtl_per_fileobject_context, ntifs/FSRTL_PER_FILEOBJECT_CONTEXT, ntifs/PFSRTL_PER_FILEOBJECT_CONTEXT"
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: FSRTL_PER_FILEOBJECT_CONTEXT, *PFSRTL_PER_FILEOBJECT_CONTEXT
f1_keywords:
 - _FSRTL_PER_FILEOBJECT_CONTEXT
 - ntifs/_FSRTL_PER_FILEOBJECT_CONTEXT
 - PFSRTL_PER_FILEOBJECT_CONTEXT
 - ntifs/PFSRTL_PER_FILEOBJECT_CONTEXT
 - FSRTL_PER_FILEOBJECT_CONTEXT
 - ntifs/FSRTL_PER_FILEOBJECT_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FSRTL_PER_FILEOBJECT_CONTEXT
 - PFSRTL_PER_FILEOBJECT_CONTEXT
 - FSRTL_PER_FILEOBJECT_CONTEXT
---

# FSRTL_PER_FILEOBJECT_CONTEXT structure

## -description

The OS uses the opaque **FSRTL_PER_FILEOBJECT_CONTEXT** structure to track file system filter-driver-defined context information structures for a file object.

## -struct-fields

### -field Links

Link for this structure in the list of all per-file-object context structures associated with the same file object. [**FsRtlInsertPerFileObjectContext**](nf-ntifs-fsrtlinsertperfileobjectcontext.md) inserts this member into the list of all per-file-object context structures for the file object.

### -field OwnerId

A pointer to a filter-driver-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the filter's device object or driver object. Note that the value of this member can't be NULL.

### -field InstanceId

A pointer to a filter-driver-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the file object itself. Note that the value of this member can be NULL.

## -remarks

File system filter drivers can use the opaque **FSRTL_PER_FILEOBJECT_CONTEXT** structure to maintain context information for a file object. This structure can be used as-is or embedded in a driver-defined, per-file-object context structure.

Each file object can have one per-file-object context structure list associated with it. Each member of this list (that is, a particular per-file-object context structure) is owned by a filter driver. From the perspective of a filter driver, each filter driver can associate multiple per-file-object context structures for the same file object.

Each filter-defined per-file-object context structure must include an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure. The FSRTL_PER_FILEOBJECT_CONTEXT structure can be allocated from paged or nonpage pool and must be initialized using the [**FsRtlInitPerFileObjectContext**](/previous-versions/ff546170(v=vs.85)) macro.

To insert a FSRTL_PER_FILEOBJECT_CONTEXT structure or a filter-defined per-file-object context structure (containing an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure) into the list of all context structures for a file object, use the [**FsRtlInsertPerFileObjectContext**](nf-ntifs-fsrtlinsertperfileobjectcontext.md) function.

After a FSRTL_PER_FILEOBJECT_CONTEXT or per-file-object context structure has been associated with a file object, it can be retrieved by calling [**FsRtlLookupPerFileObjectContext**](nf-ntifs-fsrtllookupperfileobjectcontext.md) or removed by calling [**FsRtlRemovePerFileObjectContext**](nf-ntifs-fsrtlremoveperfileobjectcontext.md) (based upon the values of **OwnerId** and **InstanceId**).

File system minifilter drivers must not use the following functions:

* [**FsRtlInitPerFileObjectContext**](/previous-versions/ff546170(v=vs.85))
* [**FsRtlInsertPerFileObjectContext**](nf-ntifs-fsrtlinsertperfileobjectcontext.md)
* [**FsRtlLookupPerFileObjectContext**](nf-ntifs-fsrtllookupperfileobjectcontext.md)
* [**FsRtlRemovePerFileObjectContext**](nf-ntifs-fsrtlremoveperfileobjectcontext.md)

Instead, minifilters can use the following functions to associate context information with a file object:

* [**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)
* [**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)
* [**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md)
* [**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md)
* [**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md)
* [**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

File system minifilter drivers must not use the **FsRtl*Xxx*PerFileObjectContext** functions. Instead, minifilters can use the **Flt*Xxx*Context** functions to associate context information with a file object. For a complete list, see the **FSRTL_PER_FILEOBJECT_CONTEXT** topic.

## -see-also

[**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md)

[**DRIVER_OBJECT**](../wdm/ns-wdm-_driver_object.md)

[**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md)

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md)

[**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md)

[**FsRtlInitPerFileObjectContext**](/previous-versions/ff546170(v=vs.85))

[**FsRtlInsertPerFileObjectContext**](nf-ntifs-fsrtlinsertperfileobjectcontext.md)

[**FsRtlLookupPerFileObjectContext**](nf-ntifs-fsrtllookupperfileobjectcontext.md)

[**FsRtlRemovePerFileObjectContext**](nf-ntifs-fsrtlremoveperfileobjectcontext.md)
