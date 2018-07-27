---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlFindInTunnelCache
title: FsRtlFindInTunnelCache function
author: windows-driver-content
description: The FsRtlFindInTunnelCache routine searches for a matching entry in the tunnel cache that matches the specified name.
old-location: ifsk\fsrtlfindintunnelcache.htm
tech.root: ifsk
ms.assetid: 80c24c5b-49a3-4ecc-92fe-3477cbb8a544
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlFindInTunnelCache, FsRtlFindInTunnelCache routine [Installable File System Drivers], fsrtlref_ae11e9b8-bc4f-4c56-84a7-8e328e215415.xml, ifsk.fsrtlfindintunnelcache, ntifs/FsRtlFindInTunnelCache
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlFindInTunnelCache
product: Windows
targetos: Windows
req.typenames: 
---

# FsRtlFindInTunnelCache function


## -description


The <b>FsRtlFindInTunnelCache</b> routine searches for a matching entry in the tunnel cache that matches the specified name.


## -parameters




### -param Cache [in]

Pointer to a tunnel cache initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546153">FsRtlInitializeTunnelCache</a>.


### -param DirectoryKey

TBD


### -param Name [in]

Pointer to a Unicode string containing the new name for the file that is being renamed or created.


### -param ShortName [out]

Pointer to a caller-allocated Unicode string to receive the short name of the tunneled file. This string must be long enough to hold a full 8.3 file name. (Unlike <i>LongName</i>, <i>ShortName</i> is not grown dynamically.)


### -param LongName [out]

Pointer to a caller-allocated Unicode string to receive the long name of the tunneled file. If this string is not large enough to hold the tunneled name, <b>FsRtlFindInTunnelCache</b> replaces it with a larger system-allocated string. If such a string is allocated, the caller is responsible for detecting this case and freeing the new system-allocated string as well as the original caller-allocated string.


### -param DataLength [in, out]

On input, this is a pointer to a variable that specifies the length of the buffer pointed to by <i>Data</i>. On output, the same variable receives the length in bytes of the data written to the buffer.


### -param Data [out]

Pointer to a caller-allocated buffer to receive the data found in the tunnel cache. 


#### - DirKey [in]

Key value of the directory containing the file that is being created or renamed.


## -returns



<b>FsRtlFindInTunnelCache</b> returns <b>TRUE</b> if a matching entry is found in the tunnel cache, <b>FALSE</b> otherwise.




## -remarks



File systems can call <b>FsRtlFindInTunnelCache</b> when a file name is added to a directory for a file that is being created or renamed. <b>FsRtlFindInTunnelCache</b> searches the tunnel cache for an entry that matches <i>DirKey</i> and <i>Name</i>. If one is found, <b>FsRtlFindInTunnelCache</b> fetches the cached information.

The match is performed as follows:

<ul>
<li>
The value of <i>DirKey</i> is compared against the entry's directory key. (This is the <i>DirectoryKey</i> value that was passed to <b>FsRtlAddToTunnelCache</b>.)

</li>
<li>
If <i>KeyByShortName</i> was set to <b>TRUE</b> in the call to <b>FsRtlAddToTunnelCache</b>, the string pointed to by <i>Name</i> is compared against the short name of the tunneled file. Otherwise, it is compared against the long name.

</li>
</ul>
The value of the buffer length variable pointed to by <i>DataLength</i> must be greater than or equal to the length in bytes of the data stored in the tunnel cache entry.

The caller is required to synchronize this call against <a href="https://msdn.microsoft.com/library/windows/hardware/ff545863">FsRtlDeleteTunnelCache</a>. In other words, a file system must ensure that it does not call <b>FsRtlFindInTunnelCache</b> and <b>FsRtlDeleteTunnelCache</b> at the same time from different threads. 

For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;id=172190">Microsoft Knowledge Base Article 172190</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545863">FsRtlDeleteTunnelCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546153">FsRtlInitializeTunnelCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

