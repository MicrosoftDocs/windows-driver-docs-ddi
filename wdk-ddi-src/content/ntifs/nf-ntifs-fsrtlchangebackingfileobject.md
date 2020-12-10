---
UID: NF:ntifs.FsRtlChangeBackingFileObject
title: FsRtlChangeBackingFileObject function (ntifs.h)
description: The FsRtlChangeBackingFileObject routine replaces the current file object with a new file object.
old-location: ifsk\fsrtlchangebackingfileobject.htm
tech.root: ifsk
ms.date: 06/08/2020
keywords: ["FsRtlChangeBackingFileObject function"]
ms.keywords: FsRtlChangeBackingFileObject, FsRtlChangeBackingFileObject routine [Installable File System Drivers], fsrtlref_4dd83ba3-8d9b-4c5b-a4ea-d7a0ceaaa9f2.xml, ifsk.fsrtlchangebackingfileobject, ntifs/FsRtlChangeBackingFileObject
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlChangeBackingFileObject routine is available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlChangeBackingFileObject
 - ntifs/FsRtlChangeBackingFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlChangeBackingFileObject
---

# FsRtlChangeBackingFileObject function


## -description

The **FsRtlChangeBackingFileObject** routine replaces the current file object with a new file object.

## -parameters

### -param CurrentFileObject

**[in, optional]** The current file object. If **CurrentFileObject** is **NULL**, the operating system's current file object is set to **NewFileObject**. If it is non-NULL, the backing file object is changed to **NewFileObject** only if the OS's current backing file object is equal to this value. If this file object does not belong to the stream, the operation fails.

### -param NewFileObject

**[in]** The new file object that the OS will reference and store internally.

### -param ChangeBackingType

**[in]** An [FSRTL_CHANGE_BACKING_TYPE](ne-ntifs-_fsrtl_change_backing_type.md) enumeration value that indicates which internal structure should be changed to reference **NewFileObject**.

### -param Flags

**[in]** Reserved for future use.

## -returns

The **FsRtlChangeBackingFileObject** routine returns STATUS_SUCCESS if the operation succeeds. Otherwise, **FsRtlChangeBackingFileObject** returns the appropriate error code.The following table contains error codes that **FsRtlChangeBackingFileObject** might return.

| Return code |Description |
| ----------- | ---------- |
| STATUS_INVALID_PARAMETER_2 | The change operation failed because the file object that **NewFileObject** specifies does not represent the same stream as CurrentFileObject.|
| STATUS_INVALID_PARAMETER_3 | The change operation failed because the caller specified an invalid backing type in **ChangeBackingType**. |
| STATUS_INVALID_PARAMETER_4 | The change operation failed because the caller specified an invalid value in **Flags**.|
| STATUS_NOT_SUPPORTED       | The change operation failed because the caller obtained the file object in a way that does not allow subsequent swapping of the file object. For example, if the caller obtained the file object with a call to **CcGetFileObjectFromSectionPtrs**, it is not safe to swap the file object.|

## -remarks

The **FsRtlChangeBackingFileObject** routine changes the file object for one of the following:

- One of the memory manager's image control areas for the stream

- The memory manager's data control area for the stream

- The cache manager's shared cache map for the stream

The **FsRtlChangeBackingFileObject** routine is not synchronous. It processes the request for a change of file object and returns immediately. The cache manager and the memory manager synchronize the change of the file object and will not free the old file object until all incomplete operations that are associated with the old file object have finished. A return status of STATUS_SUCCESS from **FsRtlChangeBackingFileObject** does not mean that the operating system has already changed the file object.

However, after **FsRtlChangeBackingFileObject** runs successfully, the operating system associates all future operations with the new file object.

To change the file object for more than one backing type, the caller must call **FsRtlChangeBackingFileObject** multiple times, one time for each backing type to change.

## -see-also

[FSRTL_CHANGE_BACKING_TYPE](ne-ntifs-_fsrtl_change_backing_type.md)

