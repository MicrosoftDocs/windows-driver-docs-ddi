---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyFullReportChange
title: FsRtlNotifyFullReportChange function
description: The FsRtlNotifyFullReportChange routine completes pending notify change IRPs.
old-location: ifsk\fsrtlnotifyfullreportchange.htm
tech.root: ifsk
ms.assetid: b0616127-6bbe-4f9b-87c6-3c7bebe60863
ms.date: 04/16/2018
ms.keywords: FsRtlNotifyFullReportChange, FsRtlNotifyFullReportChange routine [Installable File System Drivers], fsrtlref_1107429f-a697-40a9-8336-b9a145b476b9.xml, ifsk.fsrtlnotifyfullreportchange, ntifs/FsRtlNotifyFullReportChange
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
-	FsRtlNotifyFullReportChange
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlNotifyFullReportChange function


## -description


The <b>FsRtlNotifyFullReportChange</b> routine completes pending notify change IRPs. 


## -parameters




### -param NotifySync [in]

A pointer to an opaque synchronization object for the current volume.


### -param NotifyList [in]

A pointer to the head of a notify list. Each element in the list is an opaque notify structure.


### -param FullTargetName [in]

A pointer to an ANSI or Unicode string that contains the full pathname of the file.


### -param TargetNameOffset [in]

Offset within the <i>FullTargetName</i> string of the final component of the name.


### -param StreamName [in, optional]

Optional pointer to an ANSI or Unicode string that contains a stream name to store with the file name.


### -param NormalizedParentName [in, optional]

Optional pointer to an ANSI or Unicode string that contains the same path as in the <i>FullTargetName</i> string, but with all short names replaced by the corresponding long names.


### -param FilterMatch [in]

A bitmask of flags to be compared with the completion filter in the notify structure. If any of the corresponding bits in the completion filter are set, then a notify condition exists. For possible flag values, see the <i>CompletionFilter</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547026">FsRtlNotifyFullChangeDirectory</a>.


### -param Action [in]

Specifies the action code to store in the user's buffer if present. The action code can be one of the values described following.

<table>
<tr>
<th>Action Code</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_ACTION_ADDED

</td>
<td>
A new file or subdirectory has been created.

</td>
</tr>
<tr>
<td>
FILE_ACTION_REMOVED

</td>
<td>
A file or subdirectory has been deleted.

</td>
</tr>
<tr>
<td>
FILE_ACTION_MODIFIED

</td>
<td>
A file or subdirectory has been modified (but not created or deleted).

</td>
</tr>
<tr>
<td>
FILE_ACTION_RENAMED_OLD_NAME

</td>
<td>
This is the old name of a file that has been renamed.

</td>
</tr>
<tr>
<td>
FILE_ACTION_RENAMED_NEW_NAME

</td>
<td>
This is the new name of a file that has been renamed.

</td>
</tr>
<tr>
<td>
FILE_ACTION_ADDED_STREAM

</td>
<td>
A new stream has been opened.

</td>
</tr>
<tr>
<td>
FILE_ACTION_REMOVED_STREAM

</td>
<td>
A stream has been closed.

</td>
</tr>
<tr>
<td>
FILE_ACTION_MODIFIED_STREAM

</td>
<td>
A stream has been modified (but not opened or closed).

</td>
</tr>
<tr>
<td>
FILE_ACTION_REMOVED_BY_DELETE

</td>
<td>
An object ID has been removed from the index by a delete file operation.

</td>
</tr>
<tr>
<td>
FILE_ACTION_ID_NOT_TUNNELLED

</td>
<td>
An object ID for a file could not be tunneled because its object ID matched the ID of an already existing file.

</td>
</tr>
<tr>
<td>
FILE_ACTION_TUNNELLED_ID_COLLISION

</td>
<td>
An object ID for a file could not be tunneled because the file already has an object ID.

</td>
</tr>
</table>
 


### -param TargetContext [in, optional]

Context pointer to pass to the file system if performing a traverse check in the case of a tree being watched. For more information, see the <i>TraverseCallback</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547026">FsRtlNotifyFullChangeDirectory</a>.


## -returns



None




## -remarks



<b>FsRtlNotifyFullReportChange</b> is called by a file system when a file is modified so that pending notify change IRPs can be completed. 

<b>FsRtlNotifyFullReportChange</b> looks for a notify structure in the notify list that matches the specified filter and pathname. If a match is found, <b>FsRtlNotifyFullReportChange</b> completes all pending IRPs for the notify structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547026">FsRtlNotifyFullChangeDirectory</a>
 

 

