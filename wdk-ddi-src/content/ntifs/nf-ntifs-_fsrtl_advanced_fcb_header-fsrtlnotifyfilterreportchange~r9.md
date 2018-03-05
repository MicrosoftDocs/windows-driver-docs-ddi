---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyFilterReportChange~r9
title: FsRtlNotifyFilterReportChange function
author: windows-driver-content
description: FsRtlNotifyFilterReportChange completes IRP_MN_NOTIFY_CHANGE_DIRECTORY requests that are pending in the specified notify list.
old-location: ifsk\fsrtlnotifyfilterreportchange.htm
old-project: ifsk
ms.assetid: 7924405f-9862-4704-bff1-05e0285592b9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlNotifyFilterReportChange, FsRtlNotifyFilterReportChange function [Installable File System Drivers], fsrtlref_c4a79c57-aa80-40f3-9882-76ed887c99cb.xml, ifsk.fsrtlnotifyfilterreportchange, ntifs/FsRtlNotifyFilterReportChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlNotifyFilterReportChange
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyFilterReportChange function


## -description


<b>FsRtlNotifyFilterReportChange</b> completes IRP_MN_NOTIFY_CHANGE_DIRECTORY requests that are pending in the specified notify list. 


## -syntax


````
VOID FsRtlNotifyFilterReportChange(
  _In_     PNOTIFY_SYNC NotifySync,
  _In_     PLIST_ENTRY  NotifyList,
  _In_     PSTRING      FullTargetName,
  _In_     USHORT       TargetNameOffset,
  _In_opt_ PSTRING      StreamName,
  _In_opt_ PSTRING      NormalizedParentName,
  _In_     ULONG        FilterMatch,
  _In_     ULONG        Action,
  _In_opt_ PVOID        TargetContext,
  _In_opt_ PVOID        FilterContext
);
````


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

Bitmask of flags to be compared with the completion filter in the notify structure. If any of the corresponding bits in the completion filter are set, then a notify condition exists. For possible flag values, see the <i>CompletionFilter</i> parameter of <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory~r10.md">FsRtlNotifyFilterChangeDirectory</a>. 


### -param Action [in]

Specifies the action code to store in the user's buffer if present. For possible action code values, see the <i>Action</i> parameter of <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange~r8.md">FsRtlNotifyFullReportChange</a>. 


### -param TargetContext [in, optional]

Context pointer to pass to the file system if performing a traverse check in the case of a tree being watched. For more information, see the <i>TraverseCallback</i> parameter of <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory~r10.md">FsRtlNotifyFilterChangeDirectory</a>.


### -param FilterContext [in, optional]

Context pointer to pass to the filter callback routine. For more information, see the <i>FilterCallback</i> parameter of <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory~r10.md">FsRtlNotifyFilterChangeDirectory</a>. 


## -returns



None




## -remarks



A file system that has received an IRP with major function code <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>, minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY, calls <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory~r10.md">FsRtlNotifyFilterChangeDirectory</a> to create a notify structure to hold the IRP and add the notify structure to the notify list for the current volume. 

When a change occurs to the directory, the file system calls <b>FsRtlNotifyFilterReportChange</b> to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory~r10.md">FsRtlNotifyFilterChangeDirectory</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory~r9.md">FsRtlNotifyFullChangeDirectory</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange~r8.md">FsRtlNotifyFullReportChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlNotifyFilterReportChange function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

