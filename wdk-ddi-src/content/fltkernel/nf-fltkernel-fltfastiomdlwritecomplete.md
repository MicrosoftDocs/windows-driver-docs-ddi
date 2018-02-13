---
UID: NF:fltkernel.FltFastIoMdlWriteComplete
title: FltFastIoMdlWriteComplete function
author: windows-driver-content
description: The FltFastIoMdlWriteComplete routine frees the resources that FltFastIoPrepareMdlWrite allocated.
old-location: ifsk\fltfastiomdlwritecomplete.htm
old-project: ifsk
ms.assetid: 7B67BB47-6F95-4B1A-A823-F796529D5C48
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.fltfastiomdlwritecomplete, FltFastIoMdlWriteComplete, fltkernel/FsRtlMdlWriteCompleteDev, FsRtlMdlWriteCompleteDev, FsRtlMdlWriteCompleteDev routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlMdlWriteCompleteDev
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFastIoMdlWriteComplete function


## -description


The <b>FltFastIoMdlWriteComplete</b> routine frees the resources that <a href="..\fltkernel\nf-fltkernel-fltfastiopreparemdlwrite.md">FltFastIoPrepareMdlWrite</a> allocated.


## -syntax


````
BOOLEAN FsRtlMdlWriteCompleteDev(
       PFLT_INSTANCE  InitiatingInstance,
  _In_ PFILE_OBJECT   FileObject,
  _In_ PLARGE_INTEGER FileOffset,
  _In_ PMDL           MdlChain
);
````


## -parameters




### -param InitiatingInstance

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

A pointer to the file object.


### -param FileOffset [in]

A pointer to a value that specifies the starting byte offset within the cache that holds the data.


### -param MdlChain [in]

A pointer to a linked list of memory descriptor lists (MDLs) that <a href="..\fltkernel\nf-fltkernel-fltfastiopreparemdlwrite.md">FltFastIoPrepareMdlWrite</a> allocated.


## -returns



The <b>FltFastIoMdlWriteComplete</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails or if the FO_WRITE_THROUGH flag is set in the file object.




## -remarks



The <b>FltFastIoMdlWriteComplete</b> routine frees the memory descriptor lists (MDLs) that <a href="..\fltkernel\nf-fltkernel-fltfastiopreparemdlwrite.md">FltFastIoPrepareMdlWrite</a> allocated and unlocks the cache memory that <b>FltFastIoPrepareMdlWrite</b> locked.

If the FO_WRITE_THROUGH flag is set on the file object pointed to by the <i>FileObject</i> parameter, <b>FltFastIoMdlWriteComplete</b> immediately flushes the cached memory to disk. This flush operation re-enters the file system and can cause <b>FltFastIoMdlWriteComplete</b> to raise an exception if the flush operation fails. 

Each call to <a href="..\fltkernel\nf-fltkernel-fltfastiopreparemdlwrite.md">FltFastIoPrepareMdlWrite</a> must be followed by a call to <b>FltFastIoMdlWriteComplete</b>.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltfastiopreparemdlwrite.md">FltFastIoPrepareMdlWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFastIoMdlWriteComplete routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

