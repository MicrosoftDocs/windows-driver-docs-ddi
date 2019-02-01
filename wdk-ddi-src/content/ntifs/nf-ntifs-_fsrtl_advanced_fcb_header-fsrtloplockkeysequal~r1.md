---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockKeysEqual~r1
title: FsRtlOplockKeysEqual function (ntifs.h)
description: The FsRtlOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects.
old-location: ifsk\fsrtloplockkeysequal.htm
tech.root: ifsk
ms.assetid: a4adc761-cf0c-466c-b20f-0af2da9ec447
ms.date: 03/29/2018
ms.keywords: FsRtlOplockKeysEqual, FsRtlOplockKeysEqual routine [Installable File System Drivers], fsrtlref_ee1323ee-1f65-4323-8648-f613d1ac04c5.xml, ifsk.fsrtloplockkeysequal, ntifs/FsRtlOplockKeysEqual
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlOplockKeysEqual
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlOplockKeysEqual function


## -description


The <b>FsRtlOplockKeysEqual</b> routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects.


## -parameters




### -param Fo1 [in, optional]

A pointer to the first file object for the comparison.


### -param Fo2 [in, optional]

A pointer to the second file object for the comparison.


## -returns



The <b>FsRtlOplockKeysEqual</b> routine returns <b>TRUE</b> if the keys match or if the file object pointers are the same. <b>FsRtlOplockKeysEqual </b>returns <b>FALSE</b> if the keys do not match, if either of the file objects is missing, or if either of the file objects does not have a key.




## -remarks



If no oplock keys were provided when the file objects were created, they are considered to match if the file object pointers are the same (that is, they are the same file object). If the file object pointers are different and either or both of them do not have an associated oplock key, they are considered to not match.

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543408">FltOplockKeysEqual</a> instead of <b>FsRtlOplockKeysEqual</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543408">FltOplockKeysEqual</a>
 

 

