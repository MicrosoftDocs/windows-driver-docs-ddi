---
UID: NS:ntifs._FSRTL_PER_FILE_CONTEXT
title: "_FSRTL_PER_FILE_CONTEXT"
author: windows-driver-content
description: A legacy file system filter driver can use a FSRTL_PER_FILE_CONTEXT structure to associate driver-specific context information to an open file.
old-location: ifsk\fsrtl_per_file_context.htm
old-project: ifsk
ms.assetid: d20668f0-b076-4edd-bf21-98841cbbdc74
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFSRTL_PER_FILE_CONTEXT, FSRTL_PER_FILE_CONTEXT, FSRTL_PER_FILE_CONTEXT structure [Installable File System Drivers], PFSRTL_PER_FILE_CONTEXT, PFSRTL_PER_FILE_CONTEXT structure pointer [Installable File System Drivers], _FSRTL_PER_FILE_CONTEXT, contextstructures_329894da-4955-4f46-8fab-92e32f10ed0d.xml, ifsk.fsrtl_per_file_context, ntifs/FSRTL_PER_FILE_CONTEXT, ntifs/PFSRTL_PER_FILE_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting withWindows Vista.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FSRTL_PER_FILE_CONTEXT
product: Windows
targetos: Windows
req.typenames: FSRTL_PER_FILE_CONTEXT, *PFSRTL_PER_FILE_CONTEXT
---

# _FSRTL_PER_FILE_CONTEXT structure


## -description


A legacy file system filter driver can use a <b>FSRTL_PER_FILE_CONTEXT</b> structure to associate driver-specific context information to an open file.


## -syntax


````
typedef struct _FSRTL_PER_FILE_CONTEXT {
  LIST_ENTRY     Links;
  PVOID          OwnerId;
  PVOID          InstanceId;
  PFREE_FUNCTION FreeCallback;
} FSRTL_PER_FILE_CONTEXT, *PFSRTL_PER_FILE_CONTEXT;
````


## -struct-fields




### -field Links

A link for this structure in the list of all per-file context structures that are associated with the same file. <a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a> inserts this member into the list of all per-file context structures for a file. 


### -field OwnerId

A pointer to a filter-driver-allocated buffer that uniquely identifies the owner of the per-file context structure. The format of this variable is filter-driver-specific.  Filter drivers must set this member to a non-<b>NULL</b> value. 


### -field InstanceId

A pointer to a filter-driver-allocated buffer that can be used to distinguish among the per-file context structures that are created by the same filter driver. The format of this variable is filter-driver-specific. Filter drivers can set this member to <b>NULL</b>.


### -field FreeCallback

A pointer to a <a href="https://msdn.microsoft.com/291b57d9-3bef-4acb-a571-86b67a03cd08">callback routine</a> that frees the per-file context structure. Filter drivers must set this member to a non-<b>NULL</b> value.


## -remarks



In order to associate context information with a file, a legacy filter driver first allocates a <b>FSRTL_PER_FILE_CONTEXT</b> structure and initializes it using <a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a>. The driver then uses <b>FsRtlInsertPerFileContext</b> to associate that <b>FSRTL_PER_FILE_CONTEXT</b> object with the file. When the system tears down the file context object for a file, it calls <a href="..\ntifs\nf-ntifs-fsrtlteardownperfilecontexts.md">FsRtlTeardownPerFileContexts</a> which calls the <i>FreeCallback</i> routine that is specified in the <b>FSRTL_PER_FILE_CONTEXT</b> object. That callback must free the driver-specific context object.

Filter writers should choose an <b>OwnerID</b> value that is both meaningful and convenient, such as the address of a driver object or device object. 

Filter writers should choose an <b>InstanceID</b> value that is both meaningful and convenient, such as the address of the file context object for the file. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro to retrieve that address from a file object.

The <b>FSRTL_PER_FILE_CONTEXT</b> structure can be used as-is, or embedded in a driver-defined, per-file context structure.

The <b>FSRTL_PER_FILE_CONTEXT</b> structure can be allocated from paged or nonpaged pool. 

The <b>FsRtlInitPerFileContext</b> macro initializes a <b>FSRTL_PER_FILE_CONTEXT</b> structure.

Parameters

<i>FileContext</i>

<b>FSRTL_PER_FILE_CONTEXT</b>

The FSRTL_PER_FILE_CONTEXT object to be initialized.

<i>OwnerId</i>

<b>PVOID</b>

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure. The format is filter driver-specific. This parameter must have a non-<b>NULL</b> value.

<i>InstanceId</i>

<b>PVOID</b>

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure. The format is filter driver-specific. This parameter must have a non-<b>NULL</b> value.

<i>FreeCallback</i>

<b>PFREE_FUNCTION</b>

A pointer to a <a href="https://msdn.microsoft.com/291b57d9-3bef-4acb-a571-86b67a03cd08">callback routine</a> that frees the per-file context structure. 

Return value

<b>VOID</b>

None.

This macro must be used before calling <a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a>.

Filter writers should choose an <i>OwnerID</i> value that is both meaningful and convenient, such as the address of a driver object or device object. 

Filter writers should use an <i>InstanceID</i> value that is both meaningful and convenient, such as the address of the file context object for the file. Use the <b>FsRtlGetPerFileContextPointer</b> macro to retrieve that address from a file object.

For more information about how to use and create context objects, see <a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551123">PFREE_FUNCTION</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperfilecontexts.md">FsRtlTeardownPerFileContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546161">FsRtlInitPerFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_PER_FILE_CONTEXT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

