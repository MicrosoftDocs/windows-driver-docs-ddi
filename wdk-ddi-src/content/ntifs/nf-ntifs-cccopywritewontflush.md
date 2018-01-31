---
UID: NF:ntifs.CcCopyWriteWontFlush
title: CcCopyWriteWontFlush function
author: windows-driver-content
description: The CcCopyWriteWontFlush macro determines whether the amount of data to be copied in a call to CcCopyWrite is small enough not to require immediate flushing to disk if CcCopyWrite is called with Wait set to FALSE.
old-location: ifsk\cccopywritewontflush.htm
old-project: ifsk
ms.assetid: ad2b3372-f8b4-49dc-ba20-2ee89d60f41f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcCopyWriteWontFlush, ccref_a8540235-ac2e-4d04-8153-95e2dae5a650.xml, ntifs/CcCopyWriteWontFlush, CcCopyWriteWontFlush function [Installable File System Drivers], ifsk.cccopywritewontflush
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcCopyWriteWontFlush
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcCopyWriteWontFlush function


## -description


The <b>CcCopyWriteWontFlush</b> macro determines whether the amount of data to be copied in a call to <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a> is small enough not to require immediate flushing to disk if <b>CcCopyWrite</b> is called with <i>Wait</i> set to <b>FALSE</b>.


## -syntax


````
BOOLEAN CcCopyWriteWontFlush(
  _In_ PFILE_OBJECT   FileObject,
  _In_ PLARGE_INTEGER FileOffset,
  _In_ ULONG          Length
);
````


## -parameters




#### - FileObject [in]

Pointer to a file object for the cached file to which the data is to be written.


#### - FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be written.


#### - Length [in]

Length in bytes of the data to be copied.


## -returns


<b>CcCopyWriteWontFlush</b> returns <b>TRUE</b> if the amount of data to be copied in a call to <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a> is small enough not to require immediate flushing to disk, <b>FALSE</b> otherwise.



## -see-also

<a href="..\ntifs\nf-ntifs-ccdeferwrite.md">CcDeferWrite</a>

<a href="..\ntifs\nf-ntifs-cccaniwrite.md">CcCanIWrite</a>

<a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCopyWriteWontFlush function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

