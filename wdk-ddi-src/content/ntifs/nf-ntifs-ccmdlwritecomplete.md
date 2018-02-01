---
UID: NF:ntifs.CcMdlWriteComplete
title: CcMdlWriteComplete function
author: windows-driver-content
description: The CcMdlWriteComplete routine frees the memory descriptor lists (MDL) created by CcPrepareMdlWrite for a cached file.
old-location: ifsk\ccmdlwritecomplete.htm
old-project: ifsk
ms.assetid: dcd13afa-1467-407c-b843-ff88bd6526c3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/CcMdlWriteComplete, ccref_fe5a4900-c0bc-4100-b3e9-e2b7d780a9d2.xml, CcMdlWriteComplete, CcMdlWriteComplete routine [Installable File System Drivers], ifsk.ccmdlwritecomplete
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
-	CcMdlWriteComplete
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcMdlWriteComplete function


## -description


The <b>CcMdlWriteComplete</b> routine frees the memory descriptor lists (MDL) created by <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a> for a cached file.


## -syntax


````
VOID CcMdlWriteComplete(
  _In_ PFILE_OBJECT   FileObject,
  _In_ PLARGE_INTEGER FileOffset,
  _In_ PMDL           MdlChain
);
````


## -parameters




### -param FileObject [in]

File object pointer that was passed to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>.


### -param FileOffset [in]

Value of <i>FileOffset</i> that was passed to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>.


### -param MdlChain [in]

Address of the MDL chain returned by <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>.


## -returns


None



## -remarks


File systems call <b>CcMdlWriteComplete</b> to free the memory descriptor lists (MDL) created by <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a> for a cached file and to mark the specified byte range for write. All physical pages that were locked down are unlocked. Any pages that were mapped are unmapped.

If the FO_WRITE_THROUGH flag is set on the file object pointed to by the <i>FileObject</i> parameter, the file data is immediately flushed to disk. This flush operation re-enters the file system and can cause <b>CcMdlWriteComplete</b> to raise an exception if the flush operation fails. In this case, the MDL has not been freed and the caller may re-try the operation.

After <b>CcMdlWriteComplete</b> is called successfully for an IRP_MN_COMPLETE operation, the caller must set the IRP's <b>MdlAddress</b> field to <b>NULL</b>. 

Before using <b>CcMdlWriteComplete</b>, file system developers are strongly encouraged to study the way this routine is used in the FASTFAT sample. 

Each call to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a> must be followed by a call to <b>CcMdlWriteComplete</b> or <a href="..\ntifs\nf-ntifs-ccmdlwriteabort.md">CcMdlWriteAbort</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>

<a href="..\ntifs\nf-ntifs-ccmdlwriteabort.md">CcMdlWriteAbort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcMdlWriteComplete routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

