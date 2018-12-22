---
UID: NF:ntifs.FsRtlRegisterFileSystemFilterCallbacks
title: FsRtlRegisterFileSystemFilterCallbacks function
description: File system filter drivers and file systems call the FsRtlRegisterFileSystemFilterCallbacks routine to register notification callback routines to be invoked when the underlying file system performs certain operations.
old-location: ifsk\fsrtlregisterfilesystemfiltercallbacks.htm
tech.root: ifsk
ms.assetid: cd6d2ab6-ce17-47db-b5d0-4f9543e15487
ms.date: 04/16/2018
ms.keywords: FsRtlRegisterFileSystemFilterCallbacks, FsRtlRegisterFileSystemFilterCallbacks routine [Installable File System Drivers], fsrtlref_a831a0f3-f819-45e3-9121-ae50ef1b95bf.xml, ifsk.fsrtlregisterfilesystemfiltercallbacks, ntifs/FsRtlRegisterFileSystemFilterCallbacks
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlRegisterFileSystemFilterCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlRegisterFileSystemFilterCallbacks function


## -description


File system filter drivers and file systems call the <b>FsRtlRegisterFileSystemFilterCallbacks</b> routine to register notification callback routines to be invoked when the underlying file system performs certain operations. 


## -parameters




### -param FilterDriverObject [in]

A pointer to the driver object for the filter or file system driver. 


### -param Callbacks [in]

A pointer to a structure that contains the entry points of caller-supplied notification callback routines. 

This structure is defined as follows. 

<div class="alert"><b>Note</b>  All of the callback entry points are optional and can be <b>NULL</b>. </div>
<div> </div>
<div class="code"><span codelanguage="C++"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _FS_FILTER_CALLBACKS {
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
} FS_FILTER_CALLBACKS, *PFS_FILTER_CALLBACKS;</pre>
</td>
</tr>
</table></span></div>
The filter callback routine and its parameters are defined as follows: 

<div class="code"><span codelanguage="C++"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS (*PFS_FILTER_CALLBACK) (
              IN PFS_FILTER_CALLBACK_DATA Data,
              OUT PVOID *CompletionContext
              );</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Parameter</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<i>Data</i>

</td>
<td>
Pointer to the callback data structure for this operation.

</td>
</tr>
<tr>
<td>
<i>CompletionContext</i>

</td>
<td>
Context information to be passed to the filter completion callback routine. Set to <b>NULL</b> if no context information is to be passed or if there is no corresponding filter completion callback routine.

</td>
</tr>
</table>
 

The filter completion callback routine and its parameters are defined as follows: 

<div class="code"><span codelanguage="C++"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PFS_FILTER_COMPLETION_CALLBACK) (
          IN PFS_FILTER_CALLBACK_DATA Data,
          IN NTSTATUS OperationStatus,
          IN PVOID CompletionContext
          );</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Parameter</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<i>Data</i>

</td>
<td>
Pointer to the callback data structure for this operation.

</td>
</tr>
<tr>
<td>
<i>OperationStatus</i>

</td>
<td>
Status of the operation. If the file system successfully performed the operation, this parameter is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate error status value.

</td>
</tr>
<tr>
<td>
<i>CompletionContext</i>

</td>
<td>
Context information that was set in the filter callback routine. This is set to <b>NULL</b> if no information is passed or if there is no corresponding filter callback routine.

</td>
</tr>
</table>
 

The callback data structure and its members are defined as follows: 

<div class="code"><span codelanguage="C++"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _FS_FILTER_CALLBACK_DATA {
    ULONG SizeOfFsFilterCallbackData;
    UCHAR Operation;
    UCHAR Reserved;
    struct _DEVICE_OBJECT *DeviceObject;
    struct _FILE_OBJECT *FileObject;
    FS_FILTER_PARAMETERS Parameters;
} FS_FILTER_CALLBACK_DATA, *PFS_FILTER_CALLBACK_DATA;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>SizeOfFsFilterCallbackData</b>

</td>
<td>
Size of the callback data structure.

</td>
</tr>
<tr>
<td>
<b>Operation</b>

</td>
<td>
File system operation for which the callback routine is to be invoked. This operation can be one of the following: 
	<ul>
<li>FS_FILTER_ACQUIRE_FOR_SECTION_SYNCHRONIZATION</li>
<li>FS_FILTER_RELEASE_FOR_SECTION_SYNCHRONIZATION</li>
<li>FS_FILTER_ACQUIRE_FOR_MOD_WRITE</li>
<li>FS_FILTER_RELEASE_FOR_MOD_WRITE</li>
<li>FS_FILTER_ACQUIRE_FOR_CC_FLUSH</li>
<li>FS_FILTER_RELEASE_FOR_CC_FLUSH</li>
<li>FS_FILTER_QUERY_OPEN</li>
</ul>


</td>
</tr>
<tr>
<td>
<b>Reserved</b>

</td>
<td>
Reserved for system use.

</td>
</tr>
<tr>
<td>
<b>DeviceObject</b>

</td>
<td>
Device object for this operation.

</td>
</tr>
<tr>
<td>
<b>FileObject</b>

</td>
<td>
File object for this operation.

</td>
</tr>
<tr>
<td>
<b>Parameters</b>

</td>
<td>
Union containing any operation-specific parameters.

</td>
</tr>
</table>
 

The filter parameters union is defined as follows: 

<div class="code"><span codelanguage="C++"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
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
</pre>
</td>
</tr>
</table></span></div>

<table>
<tr>
<th>Parameter</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<i>EndingOffset</i>

</td>
<td>
Offset of the last byte being written plus one.

</td>
</tr>
<tr>
<td>
<i>ResourceToRelease</i>

</td>
<td>
Resource to be released. This parameter must not have a <b>NULL</b> value.

</td>
</tr>
<tr>
<td>
<i>SyncType</i>

</td>
<td>
Type of synchronization requested for the section: SyncTypeCreateSection if a section is being created, SyncTypeOther otherwise.

</td>
</tr>
<tr>
<td>
<i>PageProtection</i>

</td>
<td>
Type of page protection requested for the section. Must be zero if <i>SyncType</i> is SyncTypeOther. Otherwise, one of the following flags, possibly ORed with PAGE_NOCACHE: <ul>
<li>PAGE_NOACCESS</li>
<li>PAGE_READONLY</li>
<li>PAGE_READWRITE</li>
<li>PAGE_WRITECOPY</li>


<li>PAGE_EXECUTE</li>
<li>PAGE_EXECUTE_READ</li>
<li>PAGE_EXECUTE_READWRITE</li>
<li>PAGE_EXECUTE_WRITECOPY</li>

<li>PAGE_GUARD</li>
<li>PAGE_NOCACHE</li>
<li>PAGE_WRITECOMBINE</li>
</ul>


</td>
</tr>
<tr>

<tr>
<td>
<i>OutputInformation</i>

</td>
<td>
A [FS_FILTER_SECTION_SYNC_OUTPUT](ns-ntifs-_fs_filter_section_sync_output.md) structure that contains the extended output information for the section.
</ul>


</td>
</tr>

<tr>
<td>
<i>Irp</i>
</td>
<td>
A pointer to the IRP associated with this operation.
</td>
</tr>

<tr>
<td>
<i>FileInformation</i>
</td>
<td>
Pointer to a caller-allocated buffer into which the routine writes the requested information about the file object. The <i>FileInformationClass</i> member specifies the type of information that the caller requests.
</td>
</tr>

<tr>
<td>
<i>Length</i>
</td>
<td>
The size, in bytes, of the buffer pointed to by <i>FileInformation</i>.
</td>
</tr>

<tr>
<td>
<i>FileInformationClass</i>
</td>
<td>
Specifies the type of information to be returned about the file, in the buffer that <i>FileInformation</i> points to. Device and intermediate drivers can specify any of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff728840">FILE_INFORMATION_CLASS</a> values. Other values cause the call to fail and should not be passed to PreQueryOpen/PostQueryOpen calls.

<table>
<tr>
<th>FILE_INFORMATION_CLASS value</th>
<th>Type of information returned</th>
</tr>

<tr>
<td>
<b>FileStatInformation</b>
</td>
<td>
A [FILE_STAT_INFORMATION](ns-ntifs-_file_stat_information.md) structure. This structure contains an access mask. For more information about access masks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.
</td>
</tr>
<tr>

<tr>
<td>
<b>FileStatLxInformation</b>
</td>
<td>
A [FILE_STAT_LX_INFORMATION](ns-ntifs-_file_stat_lx_information.md) structure. This structure contains an access mask. For more information about access masks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.
</td>
</tr>
<tr>

<tr>
<td>
<b>FileCaseSensitiveInformation</b>
</td>
<td>
A [FILE_CASE_SENSITIVE_INFORMATION](ns-ntifs-_file_stat_information.md) structure.
</td>
</tr>
<tr>

</table>
</td>
</tr>

<tr>
<td>
<i>CompletionStatus</i>
</td>
<td>
<p>An NTSTATUS value that receives the final completion status and information about the operation. </p>

<p><b>CompletionStatus</b> can be set by the PostQueryOpen callback to fail the operation, since post callbacks have no return value. This is primarily used so the PostQueryOpen callback can return STATUS_FLT_DISALLOW_FSFILTER_IO to request fallback to the slow path. Doing so causes the I/O manager to service the request by performing an open/query/close of the file.</p>

<p>Similarly, the PreQueryOpen callback can return STATUS_FLT_DISALLOW_FSFILTER_IO to request fallback to the slow path.</p>
</td>
</tr>

<tr>

<td>
<i>Argument1</i>

</td>
<td>
Reserved for future use.

</td>
</tr>
<tr>
<td>
<i>Argument2</i>

</td>
<td>
Reserved for future use.

</td>
</tr>
<tr>
<td>
<i>Argument3</i>

</td>
<td>
Reserved for future use.

</td>
</tr>
<tr>
<td>
<i>Argument4</i>

</td>
<td>
Reserved for future use.

</td>
</tr>
<tr>
<td>
<i>Argument5</i>

</td>
<td>
Reserved for future use.

</td>
</tr>
</table>

<div></div>

## -returns

The <b>FsRtlRegisterFileSystemFilterCallbacks</b> routine can return one of the following status values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callback routines were successfully registered. 
</td>

</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FsRtlRegisterFileSystemFilterCallbacks</b> encountered a pool allocation failure when allocating memory to store the callback information. 

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FSFILTER_OP_COMPLETED_SUCCESSFULLY</b></dt>
</dl>
</td>
<td width="60%">
<b>FsRtlRegisterFileSystemFilterCallbacks</b> successfully completed an FsFilter operation. 

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_LOCKED_WITH_ONLY_READERS</b></dt>
</dl>
</td>
<td width="60%">
The file was locked and all users of the file can only read.

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_LOCKED_WITH_WRITERS</b></dt>
</dl>
</td>
<td width="60%">
The file was locked and at least one user of the file can write 

</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is invalid. 

</td>
</tr>
</table>

<div></div>

## -remarks

File system and file system filter drivers should call <b>FsRtlRegisterFileSystemFilterCallbacks</b> from the driver's <b>DriverEntry</b> routine.  

File systems call <b>FsRtlRegisterFileSystemFilterCallbacks</b> to set the <b>PreAcquireForSectionSynchronization</b> callback member of the FS_FILTER_CALLBACKS structure instead of using the obsolete <b>AcquireFileForNtCreateSection</b>.

<b>FsRtlRegisterFileSystemFilterCallbacks</b> registers the notification callback routines that were specified in the <i>Callbacks</i> parameter to be invoked when requests for certain file operations are sent to the underlying file system. 

Callback routines are currently defined for the following operations: 

<table>
<tr>
<th>Operation</th>
<th>Notification Callback Routine and Callback Completion Routine</th>
</tr>
<tr>
<td>
The memory manager acquires a file exclusively before creating a memory-mapped section for a portion of the file. 


<div class="alert"><b>Note</b>  For this operation, <i>SyncType</i> is set to SyncTypeCreateSection.</div>
<div> </div>


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
A kernel component (such as the cache manager) acquires a file exclusively before temporarily disabling section creation for a portion of the file. 


<div class="alert"><b>Note</b>  For this operation, <i>SyncType</i> is set to SyncTypeOther.</div>
<div> </div>


</td>
<td>

<dl>
<dt>PreAcquireForSectionSynchronization</dt>
<dt>PostAcquireForSectionSynchronization</dt>
</dl>



<div class="alert"><b>Note</b>  PreAcquireForSectionSynchronization should always return a success status code (such as STATUS_SUCCESS) for this operation. Returning any other type of status code causes the system to ASSERT on a checked build. (On free builds, the status code is ignored.)</div>
<div> </div>


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

<div class="alert"><b>Note</b>    A filter driver's notification callback routine cannot fail a request to release a file system resource. If a filter driver returns a status value other than STATUS_SUCCESS from any of the following notification callback routines, the status value is ignored. </div>
<div> </div>
<ul>
<li>
PreReleaseForSectionSynchronization 

</li>
<li>
PreReleaseForCcFlush 

</li>
<li>
PreReleaseForModifiedPageWriter 

</li>
</ul>
The filter completion callback routine is invoked after the operation request is passed to lower-level filter drivers and the underlying file system. In the completion callback routine, the filter driver must perform any needed processing and immediately return. 

The callback routines defined by <b>FsRtlRegisterFileSystemFilterCallbacks</b> supersede the following fast I/O callback routines, which are obsolete and should not be used by file system filter drivers: 

<ul>
<li>
AcquireForCcFlush

</li>
<li>
AcquireFileForNtCreateSection

</li>
<li>
AcquireForModWrite

</li>
<li>
ReleaseForCcFlush

</li>
<li>
ReleaseFileForNtCreateSection

</li>
<li>
ReleaseForModWrite

</li>
</ul>


