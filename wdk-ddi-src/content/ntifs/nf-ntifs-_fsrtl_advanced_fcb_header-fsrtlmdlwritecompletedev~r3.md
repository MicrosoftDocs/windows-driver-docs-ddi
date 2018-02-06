---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlWriteCompleteDev~r3
title: FsRtlMdlWriteCompleteDev function
author: windows-driver-content
description: The FsRtlMdlWriteCompleteDev routine frees the resources that FsRtlPrepareMdlWriteDev allocated.
old-location: ifsk\fsrtlmdlwritecompletedev.htm
old-project: ifsk
ms.assetid: 7d0525f1-8422-47a4-a64e-11e35496a849
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlMdlWriteCompleteDev, ifsk.fsrtlmdlwritecompletedev, FsRtlMdlWriteCompleteDev routine [Installable File System Drivers], fsrtlref_c0520b55-791c-4527-a734-1495a2a4809b.xml, ntifs/FsRtlMdlWriteCompleteDev
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.typenames: TOKEN_TYPE
---

# FsRtlMdlWriteCompleteDev function


## -description


The <b>FsRtlMdlWriteCompleteDev</b> routine frees the resources that <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev~r6.md">FsRtlPrepareMdlWriteDev</a> allocated.


## -syntax


````
BOOLEAN FsRtlMdlWriteCompleteDev(
  _In_     PFILE_OBJECT   FileObject,
  _In_     PLARGE_INTEGER FileOffset,
  _In_     PMDL           MdlChain,
  _In_opt_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the file object.


### -param FileOffset [in]

A pointer to a value that specifies the starting byte offset within the cache that holds the data.


### -param MdlChain [in]

A pointer to a linked list of memory descriptor lists (MDLs) that <b>FsRtlPrepareMdlWrite</b> allocated.


### -param DeviceObject [in, optional]

The device object for the device that holds the file data.


## -returns


The <b>FsRtlMdlWriteCompleteDev</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails or if the FO_WRITE_THROUGH flag is set in the file object.



## -remarks


The <b>FsRtlMdlWriteCompleteDev</b> routine frees the memory descriptor lists (MDLs) that <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev~r6.md">FsRtlPrepareMdlWriteDev</a> allocated and unlocks the cache memory that <b>FsRtlPrepareMdlWriteDev</b> locked.

If the FO_WRITE_THROUGH flag is set on the file object pointed to by the <i>FileObject</i> parameter, <b>FsRtlMdlWriteCompleteDev</b> immediately flushes the cached memory to disk. This flush operation re-enters the file system and can cause <b>FsRtlMdlWriteCompleteDev</b> to raise an exception if the flush operation fails. 

Each call to <b>FsRtlPrepareMdlWrite</b> must be followed by a call to <b>FsRtlMdlWriteCompleteDev</b>.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev~r6.md">FsRtlPrepareMdlWriteDev</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlMdlWriteCompleteDev routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

