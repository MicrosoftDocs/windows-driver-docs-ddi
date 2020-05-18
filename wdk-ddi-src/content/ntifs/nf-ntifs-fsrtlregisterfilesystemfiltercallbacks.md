---
UID: NF:ntifs.FsRtlRegisterFileSystemFilterCallbacks
title: FsRtlRegisterFileSystemFilterCallbacks function (ntifs.h)
description: File system filter drivers and file systems call the FsRtlRegisterFileSystemFilterCallbacks routine to register notification callback routines to be invoked when the underlying file system performs certain operations.
old-location: ifsk\fsrtlregisterfilesystemfiltercallbacks.htm
tech.root: ifsk
ms.assetid: cd6d2ab6-ce17-47db-b5d0-4f9543e15487
ms.date: 12/15/2019
keywords: ["FsRtlRegisterFileSystemFilterCallbacks function"]
ms.keywords: FsRtlRegisterFileSystemFilterCallbacks, FsRtlRegisterFileSystemFilterCallbacks routine [Installable File System Drivers], fsrtlref_a831a0f3-f819-45e3-9121-ae50ef1b95bf.xml, ifsk.fsrtlregisterfilesystemfiltercallbacks, ntifs/FsRtlRegisterFileSystemFilterCallbacks
f1_keywords:
 - "ntifs/FsRtlRegisterFileSystemFilterCallbacks"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later versions of the Windows operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlRegisterFileSystemFilterCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlRegisterFileSystemFilterCallbacks function

## -description

File system filter drivers and file systems call the **FsRtlRegisterFileSystemFilterCallbacks** routine to register notification callback routines to be invoked when the underlying file system performs certain operations.

## -parameters

### -param FilterDriverObject [in]

A pointer to the driver object for the filter or file system driver.

### -param Callbacks [in]

A pointer to a structure that contains the entry points of caller-supplied notification callback routines.

This structure is defined as follows.

> [!NOTE]
> All of the callback entry points are optional and can be **NULL**.

```cpp

typedef struct _FS_FILTER_CALLBACKS {
    ULONG SizeOfFsFilterCallbacks;
    ULONG Reserved;
    PFS_FILTER_CALLBACK PreAcquireForSectionSynchronization;
    PFS_FILTER_COMPLETION_CALLBACK PostAcquireForSectionSynchronization;
    PFS_FILTER_CALLBACK PreReleaseForSectionSynchronization;
    PFS_FILTER_COMPLETION_CALLBACK PostReleaseForSectionSynchronization;
    PFS_FILTER_CALLBACK PreAcquireForCcFlush;
    PFS_FILTER_COMPLETION_CALLBACK PostAcquireForCcFlush;
    PFS_FILTER_CALLBACK PreReleaseForCcFlush;
    PFS_FILTER_COMPLETION_CALLBACK PostReleaseForCcFlush;
    PFS_FILTER_CALLBACK PreAcquireForModifiedPageWriter;
    PFS_FILTER_COMPLETION_CALLBACK PostAcquireForModifiedPageWriter;
    PFS_FILTER_CALLBACK PreReleaseForModifiedPageWriter;
    PFS_FILTER_COMPLETION_CALLBACK PostReleaseForModifiedPageWriter;
    PFS_FILTER_CALLBACK PreQueryOpen;
    PFS_FILTER_COMPLETION_CALLBACK PostQueryOpen;
} FS_FILTER_CALLBACKS, *PFS_FILTER_CALLBACKS;

```

The filter callback routine and its parameters are defined as follows:

```cpp

typedef
NTSTATUS (*PFS_FILTER_CALLBACK) (
              IN PFS_FILTER_CALLBACK_DATA Data,
              OUT PVOID *CompletionContext
              );

```

| Parameter | Meaning |
| --------- | ------- |
| *Data*    | Pointer to the callback data structure for this operation. |
| *CompletionContext* | Context information to be passed to the filter completion callback routine. Set to **NULL** if no context information is to be passed or if there is no corresponding filter completion callback routine. |

The filter completion callback routine and its parameters are defined as follows:

```cpp

typedef
VOID (*PFS_FILTER_COMPLETION_CALLBACK) (
          IN PFS_FILTER_CALLBACK_DATA Data,
          IN NTSTATUS OperationStatus,
          IN PVOID CompletionContext
          );

```

| Parameter | Meaning |
| --------- | ------- |
| *Data*    | Pointer to the callback data structure for this operation. |
| *OperationStatus* | Status of the operation. If the file system successfully performed the operation, this parameter is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate error status value. |
| *CompletionContext* | Context information that was set in the filter callback routine. This is set to **NULL** if no information is passed or if there is no corresponding filter callback routine. |

The *Data* callback data structure and its members are defined as follows:

```cpp

typedef struct _FS_FILTER_CALLBACK_DATA {
    ULONG SizeOfFsFilterCallbackData;
    UCHAR Operation;
    UCHAR Reserved;
    struct _DEVICE_OBJECT *DeviceObject;
    struct _FILE_OBJECT *FileObject;
    FS_FILTER_PARAMETERS Parameters;
} FS_FILTER_CALLBACK_DATA, *PFS_FILTER_CALLBACK_DATA;

```

| Member | Meaning |
| ------ | ------- |
| **SizeOfFsFilterCallbackData** | Size of the callback data structure. |
| **Operation** | File system operation for which the callback routine is to be invoked. This operation can be one of: FS_FILTER_ACQUIRE_FOR_SECTION_SYNCHRONIZATION, FS_FILTER_RELEASE_FOR_SECTION_SYNCHRONIZATION, FS_FILTER_ACQUIRE_FOR_MOD_WRITE, FS_FILTER_RELEASE_FOR_MOD_WRITE FS_FILTER_ACQUIRE_FOR_CC_FLUSH, FS_FILTER_RELEASE_FOR_CC_FLUSH FS_FILTER_QUERY_OPEN |
| **Reserved** | Reserved for system use. |
| **DeviceObject** | Device object for this operation. |
| **FileObject** | File object for this operation. |
| **Parameters** | Union containing any operation-specific parameters. |

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

* **AcquireForSectionSynchronization**:
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

  * **OutputInformation**: An [**FS_FILTER_SECTION_SYNC_OUTPUT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fs_filter_section_sync_output) structure that contains the extended output information for the section.

  * **Flags**: When **SyncType** is **SyncTypeCreateSection**, **Flags** can be one of the following values:

    * FS_FILTER_SECTION_SYNC_IN_FLAG_DONT_UPDATE_LAST_ACCESS  (0x00000001): The file system should not update the last access time for access to the file through the section that's being created.
    * FS_FILTER_SECTION_SYNC_IN_FLAG_DONT_UPDATE_LAST_WRITE  (0x00000002): The file system should not update the last write time for modifications to the file through the section that is being created.

* **QueryOpen**
  * **Irp**: Pointer to the IRP associated with this operation.
  * **FileInformation**: Pointer to a caller-allocated buffer into which the routine writes the requested information about the file object. The **FileInformationClass** member specifies the type of information that the caller requests.
  * **Length**: The size, in bytes, of the buffer pointed to by **FileInformation**.
  * **CompletionStatus**: An NTSTATUS value that receives the final completion status and information about the operation. **CompletionStatus** can be set by the PostQueryOpen callback to fail the operation, since post callbacks have no return value. This is primarily used so the PostQueryOpen callback can return STATUS_FLT_DISALLOW_FSFILTER_IO to request fallback to the slow path. Doing so causes the I/O manager to service the request by performing an open/query/close of the file. Similarly, the PreQueryOpen callback can return STATUS_FLT_DISALLOW_FSFILTER_IO to request fallback to the slow path.

  * **FileInformationClass**: Type of information to be returned about the file, in the buffer that **FileInformation** points to. Device and intermediate drivers can specify any of the following [**FILE_INFORMATION_CLASS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class) values. Other values cause the call to fail and should not be passed to PreQueryOpen/PostQueryOpen calls.
  
| FILE_INFORMATION_CLASS value | Type of information returned |
| ---------------------------- | ---------------------------- |
| **FileStatInformation** | A [FILE_STAT_INFORMATION](ns-ntifs-_file_stat_information.md) structure. This structure contains an access mask. For more information about access masks, see [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask). |
| **FileStatLxInformation** | A [FILE_STAT_LX_INFORMATION](ns-ntifs-_file_stat_lx_information.md) structure. This structure contains an access mask. For more information about access masks, see [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask). |
| **FileCaseSensitiveInformation** | A [FILE_CASE_SENSITIVE_INFORMATION](ns-ntifs-_file_stat_information.md) structure.

* **Others**
  * **Argument1**: Reserved for future use.
  * **Argument2**: Reserved for future use.
  * **Argument3**: Reserved for future use.
  * **Argument4**: Reserved for future use.
  * **Argument5**: Reserved for future use.

## -returns

The **FsRtlRegisterFileSystemFilterCallbacks** routine can return one of the following status values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The callback routines were successfully registered. |
| STATUS_INSUFFICIENT_RESOURCES | **FsRtlRegisterFileSystemFilterCallbacks** encountered a pool allocation failure when allocating memory to store the callback information. |
| STATUS_FSFILTER_OP_COMPLETED_SUCCESSFULLY | **FsRtlRegisterFileSystemFilterCallbacks** successfully completed an FsFilter operation. |
| STATUS_FILE_LOCKED_WITH_ONLY_READERS | The file was locked and all users of the file can only read. |
| STATUS_FILE_LOCKED_WITH_WRITERS | The file was locked and at least one user of the file can write |
| STATUS_INVALID_PARAMETER | One of the parameters is invalid. |

## -remarks

File system and file system filter drivers should call **FsRtlRegisterFileSystemFilterCallbacks** from the driver's **DriverEntry** routine.  

File systems call **FsRtlRegisterFileSystemFilterCallbacks** to set the **PreAcquireForSectionSynchronization** callback member of the FS_FILTER_CALLBACKS structure instead of using the obsolete **AcquireFileForNtCreateSection**.

**FsRtlRegisterFileSystemFilterCallbacks** registers the notification callback routines that were specified in the **Callbacks** parameter to be invoked when requests for certain file operations are sent to the underlying file system.

Callback routines are currently defined for the following operations:

<table>
<tr>
<th>Operation</th>
<th>Notification Callback Routine and Callback Completion Routine</th>
</tr>
<tr>
<td>
The memory manager acquires a file exclusively before creating a memory-mapped section for a portion of the file. For this operation, <i>SyncType</i> is set to SyncTypeCreateSection.

</td>
<td>

<dl>
<dt>PreAcquireForSectionSynchronization</dt>
<dt>PostAcquireForSectionSynchronization</dt>
</dl>

</td>
</tr>
<tr>
<td>
The memory manager releases a file after creating a memory-mapped section for a portion of the file.

</td>
<td>

<dl>
<dt>PreReleaseForSectionSynchronization</dt>
<dt>PostReleaseForSectionSynchronization</dt>
</dl>

</td>
</tr>
<tr>
<td>
A kernel component (such as the cache manager) acquires a file exclusively before temporarily disabling section creation for a portion of the file. For this operation, <i>SyncType</i> is set to SyncTypeOther.

</td>
<td>

<dl>
<dt>PreAcquireForSectionSynchronization</dt>
<dt>PostAcquireForSectionSynchronization</dt>
</dl>

PreAcquireForSectionSynchronization should always return a success status code (such as STATUS_SUCCESS) for this operation. Returning any other type of status code causes the system to ASSERT on a checked build. (On free builds, the status code is ignored.)

</td>
</tr>
<tr>
<td>
A kernel component (such as the cache manager) releases a file after temporarily disabling section creation for a portion of the file.

</td>
<td>

<dl>
<dt>PreReleaseForSectionSynchronization</dt>
<dt>PostReleaseForSectionSynchronization</dt>
</dl>

</td>
</tr>
<tr>
<td>
The cache manager acquires a file exclusively before flushing a portion of the file from the cache.

</td>
<td>

<dl>
<dt>PreAcquireForCcFlush</dt>
<dt>PostAcquireForCcFlush</dt>
</dl>

</td>
</tr>
<tr>
<td>
The cache manager releases a file after flushing a portion of the file from the cache.

</td>
<td>

<dl>
<dt>PreReleaseForCcFlush</dt>
<dt>PostReleaseForCcFlush</dt>
</dl>

</td>
</tr>
<tr>
<td>
The modified page writer acquires a file exclusively before writing a portion of the file to disk.

</td>
<td>

<dl>
<dt>PreAcquireForModifiedPageWriter</dt>
<dt>PostAcquireForModifiedPageWriter</dt>
</dl>

</td>
</tr>
<tr>
<td>
The modified page writer releases a file after writing a portion of the file to disk.

</td>
<td>

<dl>
<dt>PreReleaseForModifiedPageWriter</dt>
<dt>PostReleaseForModifiedPageWriter</dt>
</dl>

</td>
</tr>

<tr>
<td>
A component queries for file information by name without opening the file.

</td>
<td>

<dl>
<dt>PreQueryOpen</dt>
<dt>PostQueryOpen</dt>
</dl>

</td>
</tr>

</table>

The filter notification callback routine is invoked before the operation request is passed to lower-level filter drivers and the underlying file system. In the callback routine, the filter driver should perform any needed processing and immediately return STATUS_SUCCESS. If a filter driver's callback routine returns a status value other than STATUS_SUCCESS, this causes the operation request to fail. Repeated failure of certain requests, such as locking requests, can halt system progress. Thus, filter drivers should fail such a request only when absolutely necessary. When failing these requests, the filter driver should return an error status value that describes the error as completely and accurately as possible.

> [!NOTE]
>
> A filter driver's notification callback routine cannot fail a request to release a file system resource. If a filter driver returns a status value other than STATUS_SUCCESS from any of the following notification callback routines, the status value is ignored.
>
> * PreReleaseForSectionSynchronization
> * PreReleaseForCcFlush
> * PreReleaseForModifiedPageWriter

The filter completion callback routine is invoked after the operation request is passed to lower-level filter drivers and the underlying file system. In the completion callback routine, the filter driver must perform any needed processing and immediately return.

The callback routines defined by **FsRtlRegisterFileSystemFilterCallbacks** supersede the following fast I/O callback routines, which are obsolete and should not be used by file system filter drivers:

* AcquireForCcFlush
* AcquireFileForNtCreateSection
* AcquireForModWrite
* ReleaseForCcFlush
* ReleaseFileForNtCreateSection
* ReleaseForModWrite
