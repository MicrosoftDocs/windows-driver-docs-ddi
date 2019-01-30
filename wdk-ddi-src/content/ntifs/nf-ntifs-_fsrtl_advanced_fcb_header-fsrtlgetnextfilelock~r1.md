---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlGetNextFileLock~r1
title: FsRtlGetNextFileLock function (ntifs.h)
description: The FsRtlGetNextFileLock routine is used to enumerate the byte-range locks that currently exist for a specified file.
old-location: ifsk\fsrtlgetnextfilelock.htm
tech.root: ifsk
ms.assetid: 175fa4a7-a8e0-4fb1-8103-e513ea8c0778
ms.date: 03/29/2018
ms.keywords: FsRtlGetNextFileLock, FsRtlGetNextFileLock routine [Installable File System Drivers], fsrtlref_d34dc7b6-7bdd-47a8-a35e-302c621bf93d.xml, ifsk.fsrtlgetnextfilelock, ntifs/FsRtlGetNextFileLock
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlGetNextFileLock
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetNextFileLock function


## -description


The <b>FsRtlGetNextFileLock</b> routine is used to enumerate the byte-range locks that currently exist for a specified file.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <b>FsRtlAllocateFileLock</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>.


### -param Restart [in]

Set to <b>TRUE</b> if the enumeration is to start at the beginning of the list of byte range locks. Set to <b>FALSE</b> if resuming the enumeration from a previous call.

To enumerate all byte-range locks for a given file, use <b>FsRtlGetNextFileLock</b> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>for (p = FsRtlGetNextFileLock( FileLock, TRUE );
     p != NULL;
     p = FsRtlGetNextFileLock( FileLock, FALSE )) {
        // Process the lock information pointed to by p
}</pre>
</td>
</tr>
</table></span></div>

## -returns



<b>FsRtlGetNextFileLock</b> returns a pointer to the FILE_LOCK_INFO structure for the next byte-range lock, if one exists. If there are no more byte-range locks for this file, <b>FsRtlGetNextFileLock</b> returns <b>NULL</b>.




## -remarks



The byte range locks are not enumerated in any particular order.

Note that because the current enumeration state is stored in the FILE_LOCK structure, callers must be careful to synchronize calls to <b>FsRtlGetNextFileLock</b>, and to avoid modifying any of the structures that it returns. If multiple threads attempt to use <b>FsRtlGetNextFileLock</b> at the same time, the results will be unpredictable, and the enumeration will not be reliably complete.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545697">FsRtlAreThereCurrentFileLocks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545758">FsRtlCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545760">FsRtlCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545918">FsRtlFastCheckLockForRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545928">FsRtlFastCheckLockForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545940">FsRtlFastLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545947">FsRtlFastUnlockAll</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545954">FsRtlFastUnlockAllByKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545958">FsRtlFastUnlockSingle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546122">FsRtlInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547166">FsRtlProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547313">FsRtlUninitializeFileLock</a>
 

 

