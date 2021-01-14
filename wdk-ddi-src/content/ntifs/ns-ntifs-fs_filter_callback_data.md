---
UID: NS:ntifs._FS_FILTER_CALLBACK_DATA
title: FS_FILTER_CALLBACK_DATA
ms.date: 11/23/2020
tech.root: ifsk
ms.topic: language-reference
targetos: Windows
description: FS_FILTER_CALLBACK_DATA is the callback data structure for a FS_FILTER_CALLBACKS's FS_FILTER_CALLBACK or FS_FILTER_COMPLETION_CALLBACK operation.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: FS_FILTER_CALLBACK_DATA, *PFS_FILTER_CALLBACK_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FS_FILTER_CALLBACK_DATA
 - FS_FILTER_CALLBACK_DATA
f1_keywords:
 - _FS_FILTER_CALLBACK_DATA
 - ntifs/_FS_FILTER_CALLBACK_DATA
 - PFS_FILTER_CALLBACK_DATA
 - ntifs/PFS_FILTER_CALLBACK_DATA
 - FS_FILTER_CALLBACK_DATA
 - ntifs/FS_FILTER_CALLBACK_DATA
dev_langs:
 - c++
---

## -description

FS_FILTER_CALLBACK_DATA is the callback data structure for a [**FS_FILTER_CALLBACKS**](ns-ntifs-fs_filter_callbacks.md)'s FS_FILTER_CALLBACK or FS_FILTER_COMPLETION_CALLBACK operation.

## -struct-fields

### -field SizeOfFsFilterCallbackData

Size of this structure, in bytes. Set to ```sizeof(FS_FILTER_CALLBACK_DATA)```.

### -field Operation

File system operation for which the callback routine is to be invoked. This operation can be one of:

* FS_FILTER_ACQUIRE_FOR_SECTION_SYNCHRONIZATION
* FS_FILTER_RELEASE_FOR_SECTION_SYNCHRONIZATION
* FS_FILTER_ACQUIRE_FOR_MOD_WRITE
* FS_FILTER_RELEASE_FOR_MOD_WRITE
* FS_FILTER_ACQUIRE_FOR_CC_FLUSH
* FS_FILTER_RELEASE_FOR_CC_FLUSH FS_FILTER_QUERY_OPEN

### -field Reserved

Reserved for system use.

### -field DeviceObject

Device object for this operation.

### -field FileObject

File object for this operation.

### -field Parameters

Union containing any operation-specific parameters. See Remarks.

## -remarks

is a member of the [**FS_FILTER_CALLBACKS**](ns-ntifs-fs_filter_callbacks.md) structure, which is passed to [**FsRtlRegisterFileSystemFilterCallbacks**](nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md) in a file system or filter driver's **DriverEntry** routine.

The **Parameters** union is defined as follows:

```cpp

typedef union _FS_FILTER_PARAMETERS {
    //
    //  AcquireForModifiedPageWriter
    //
    struct {
        PLARGE_INTEGER EndingOffset;
        PERESOURCE *ResourceToRelease;
    } AcquireForModifiedPageWriter;

    //
    //  ReleaseForModifiedPageWriter
    //
    struct {
        PERESOURCE ResourceToRelease;
    } ReleaseForModifiedPageWriter;

    //
    //  AcquireForSectionSynchronization
    //
    struct {
        FS_FILTER_SECTION_SYNC_TYPE SyncType;
        ULONG PageProtection;
        PFS_FILTER_SECTION_SYNC_OUTPUT OutputInformation;
        ULONG Flags;
    } AcquireForSectionSynchronization;

    //
    // QueryOpen
    //
    struct {
        PIRP Irp;
        PVOID FileInformation;
        PULONG Length;
        FILE_INFORMATION_CLASS FileInformationClass;
        NTSTATUS CompletionStatus;
    } QueryOpen;

    //
    //  Other
    //
    struct {
        PVOID Argument1;
        PVOID Argument2;
        PVOID Argument3;
        PVOID Argument4;
        PVOID Argument5;
    } Others;
} FS_FILTER_PARAMETERS, *PFS_FILTER_PARAMETERS;

```

Structure members of the FS_FILTER_PARAMETERS union are described as follows.

* **AcquireForModifiedPageWriter**

  * **EndingOffset**: Offset of the last byte being written plus one.
  * **ResourceToRelease**: Resource to be released. This parameter must not have a **NULL** value.

* **ReleaseForModifiedPageWriter**
  * **ResourceToRelease**: Resource to be released. This parameter must not have a **NULL** value.

* **AcquireForSectionSynchronization**

  * **SyncType**: Type of synchronization requested for the section. Set to **SyncTypeCreateSection** if a section is being created; **SyncTypeOther** otherwise.
  * **PageProtection**: Type of page protection requested for the section. Must be zero if **SyncType** is **SyncTypeOther**. Otherwise, one of the following flags, possibly ORed with PAGE_NOCACHE:

    * PAGE_NOACCESS
    * PAGE_READONLY
    * PAGE_READWRITE
    * PAGE_WRITECOPY
    * PAGE_EXECUTE
    * PAGE_EXECUTE_READ
    * PAGE_EXECUTE_READWRITE
    * PAGE_EXECUTE_WRITECOPY
    * PAGE_GUARD
    * PAGE_NOCACHE
    * PAGE_WRITECOMBINE

  * **OutputInformation**: An [**FS_FILTER_SECTION_SYNC_OUTPUT**](./ns-ntifs-_fs_filter_section_sync_output.md) structure that contains the extended output information for the section.

  * **Flags**: When **SyncType** is **SyncTypeCreateSection**, **Flags** can be one of the following values:

    * FS_FILTER_SECTION_SYNC_IN_FLAG_DONT_UPDATE_LAST_ACCESS  (0x00000001): The file system should not update the last access time for access to the file through the section that's being created.
    * FS_FILTER_SECTION_SYNC_IN_FLAG_DONT_UPDATE_LAST_WRITE  (0x00000002): The file system should not update the last write time for modifications to the file through the section that is being created.

* **QueryOpen**

  * **Irp**: Pointer to the IRP associated with this operation.
  * **FileInformation**: Pointer to a caller-allocated buffer into which the routine writes the requested information about the file object. The **FileInformationClass** member specifies the type of information that the caller requests.
  * **Length**: The size, in bytes, of the buffer pointed to by **FileInformation**.
  * **CompletionStatus**: An NTSTATUS value that receives the final completion status and information about the operation. **CompletionStatus** can be set by the PostQueryOpen callback to fail the operation, since post callbacks have no return value. This is primarily used so the PostQueryOpen callback can return STATUS_FLT_DISALLOW_FSFILTER_IO to request fallback to the slow path. Doing so causes the I/O manager to service the request by performing an open/query/close of the file. Similarly, the PreQueryOpen callback can return STATUS_FLT_DISALLOW_FSFILTER_IO to request fallback to the slow path.

  * **FileInformationClass**: Type of information to be returned about the file, in the buffer that **FileInformation** points to. Device and intermediate drivers can specify any of the following [**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md) values. Other values cause the call to fail and should not be passed to PreQueryOpen/PostQueryOpen calls.
  
   | FILE_INFORMATION_CLASS value | Type of information returned |
   | ---------------------------- | ---------------------------- |
   | **FileStatInformation** | A [FILE_STAT_INFORMATION](ns-ntifs-_file_stat_information.md) structure. This structure contains an access mask. For more information about access masks, see [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask). |
   | **FileStatLxInformation** | A [FILE_STAT_LX_INFORMATION](ns-ntifs-_file_stat_lx_information.md) structure. This structure contains an access mask. For more information about access masks, see [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask). |
   | **FileCaseSensitiveInformation** | A [FILE_CASE_SENSITIVE_INFORMATION](ns-ntifs-_file_stat_information.md) structure.

* **Others**
  * **Argument1**: Reserved for future use.
  * **Argument2**: Reserved for future use.
  * **Argument3**: Reserved for future use.
  * **Argument4**: Reserved for future use.
  * **Argument5**: Reserved for future use.

## -see-also

[**FS_FILTER_CALLBACKS**](ns-ntifs-fs_filter_callbacks.md)

[**FsRtlRegisterFileSystemFilterCallbacks**](nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md)

