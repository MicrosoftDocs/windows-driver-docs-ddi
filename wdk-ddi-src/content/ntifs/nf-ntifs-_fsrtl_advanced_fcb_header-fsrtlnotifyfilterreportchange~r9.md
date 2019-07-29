---
UID: NF:ntifs.FsRtlNotifyFilterReportChange~r9
title: FsRtlNotifyFilterReportChange function (ntifs.h)
description: FsRtlNotifyFilterReportChange completes IRP_MN_NOTIFY_CHANGE_DIRECTORY requests that are pending in the specified notify list.
old-location: ifsk\fsrtlnotifyfilterreportchange.htm
tech.root: ifsk
ms.assetid: 7924405f-9862-4704-bff1-05e0285592b9
ms.date: 03/29/2018
ms.keywords: FsRtlNotifyFilterReportChange, FsRtlNotifyFilterReportChange function [Installable File System Drivers], fsrtlref_c4a79c57-aa80-40f3-9882-76ed887c99cb.xml, ifsk.fsrtlnotifyfilterreportchange, ntifs/FsRtlNotifyFilterReportChange
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlNotifyFilterReportChange"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
req.irql: "< APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlNotifyFilterReportChange
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyFilterReportChange function


## -description


<b>FsRtlNotifyFilterReportChange</b> completes IRP_MN_NOTIFY_CHANGE_DIRECTORY requests that are pending in the specified notify list.


## -parameters




### -param NotifySync [in]

Pointer to an opaque synchronization object for the change directory notify list that is pointed to by the <i>NotifyList</i> parameter.


### -param NotifyList [in]

Pointer to the head of the change directory notify list for the current volume. Each element in the list is an opaque notify structure.


### -param FullTargetName [in]

Pointer to an ANSI or Unicode string that contains the full pathname of the file or directory that changed.


### -param TargetNameOffset [in]

Offset, in bytes, within the <i>FullTargetName</i> string of the final component of the file name for the file or directory that changed.


### -param StreamName [in, optional]

Optional pointer to an ANSI or Unicode string that contains a stream name to store with the file name.


### -param NormalizedParentName [in, optional]

Optional pointer to an ANSI or Unicode string that contains the same path as in the <i>FullTargetName</i> string, but with all short names replaced by the corresponding long names.


### -param FilterMatch [in]

Bitmask of flags to be compared with the completion filter in the notify structure. If any of the corresponding bits in the completion filter are set, then a notify condition exists. For possible flag values, see the <i>CompletionFilter</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>.


### -param Action [in]

Specifies the action code to store in the user's buffer if present. For possible action code values, see the <i>Action</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>.


### -param TargetContext [in, optional]

Context pointer to pass to the file system if performing a traverse check in the case of a tree being watched. For more information, see the <i>TraverseCallback</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>.


### -param FilterContext [in, optional]

Context pointer to pass to the filter callback routine. For more information, see the <i>FilterCallback</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>.


## -returns



None




## -remarks



A file system that has received an IRP with major function code <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>, minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY, calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a> to create a notify structure to hold the IRP and add the notify structure to the notify list for the current volume.

When a change occurs to the directory, the file system calls <b>FsRtlNotifyFilterReportChange</b> to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory">FsRtlNotifyFullChangeDirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>
 

 

