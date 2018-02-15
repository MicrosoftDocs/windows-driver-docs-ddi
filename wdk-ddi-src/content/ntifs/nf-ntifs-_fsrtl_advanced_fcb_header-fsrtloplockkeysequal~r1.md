---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockKeysEqual~r1
title: FsRtlOplockKeysEqual function
author: windows-driver-content
description: The FsRtlOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects.
old-location: ifsk\fsrtloplockkeysequal.htm
old-project: ifsk
ms.assetid: a4adc761-cf0c-466c-b20f-0af2da9ec447
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fsrtlref_ee1323ee-1f65-4323-8648-f613d1ac04c5.xml, FsRtlOplockKeysEqual, ntifs/FsRtlOplockKeysEqual, FsRtlOplockKeysEqual routine [Installable File System Drivers], ifsk.fsrtloplockkeysequal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockKeysEqual routine is available starting with Windows 7.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlOplockKeysEqual
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlOplockKeysEqual function


## -description


The <b>FsRtlOplockKeysEqual</b> routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. 


## -syntax


````
BOOLEAN FsRtlOplockKeysEqual(
  _In_opt_ PFILE_OBJECT Fo1,
  _In_opt_ PFILE_OBJECT Fo2
);
````


## -parameters




### -param Fo1 [in, optional]

A pointer to the first file object for the comparison. 


### -param Fo2 [in, optional]

A pointer to the second file object for the comparison. 


## -returns



The <b>FsRtlOplockKeysEqual</b> routine returns <b>TRUE</b> if the keys match or if the file object pointers are the same. <b>FsRtlOplockKeysEqual </b>returns <b>FALSE</b> if the keys do not match, if either of the file objects is missing, or if either of the file objects does not have a key. 




## -remarks



If no oplock keys were provided when the file objects were created, they are considered to match if the file object pointers are the same (that is, they are the same file object). If the file object pointers are different and either or both of them do not have an associated oplock key, they are considered to not match.

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltoplockkeysequal.md">FltOplockKeysEqual</a> instead of <b>FsRtlOplockKeysEqual</b>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltoplockkeysequal.md">FltOplockKeysEqual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlOplockKeysEqual routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

