---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAddToTunnelCache~r6
title: FsRtlAddToTunnelCache function
author: windows-driver-content
description: The FsRtlAddToTunnelCache routine caches a file name that is removed from a directory when a file is renamed or deleted.
old-location: ifsk\fsrtladdtotunnelcache.htm
old-project: ifsk
ms.assetid: 71cac8fd-d544-4f66-a3ba-f0b267e46d1e
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.fsrtladdtotunnelcache, fsrtlref_85021948-2f5a-4462-8222-ddc25ed86f97.xml, ntifs/FsRtlAddToTunnelCache, FsRtlAddToTunnelCache, FsRtlAddToTunnelCache routine [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlAddToTunnelCache
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAddToTunnelCache function


## -description


The <b>FsRtlAddToTunnelCache</b> routine caches a file name that is removed from a directory when a file is renamed or deleted.


## -syntax


````
VOID FsRtlAddToTunnelCache(
  _In_ TUNNEL         *Cache,
  _In_ ULONGLONG      DirectoryKey,
  _In_ UNICODE_STRING *ShortName,
  _In_ UNICODE_STRING *LongName,
  _In_ BOOLEAN        KeyByShortName,
  _In_ ULONG          DataLength,
  _In_ VOID           *Data
);
````


## -parameters




### -param Cache [in]

Pointer to a tunnel cache initialized by <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md">FsRtlInitializeTunnelCache</a>.


### -param DirectoryKey [in]

Key value of the directory containing the file that is being deleted or renamed. The directory key is a unique unsigned 64-bit identifier that is generated and assigned to the directory by the file system.


### -param ShortName [in]

Unicode string containing the short (8.3) name for the file. If <i>KeyByShortName</i> is <b>FALSE</b>, <i>ShortName</i> is optional.


### -param LongName [in]

Unicode string containing the long name for the file. A long file name is a name for a file or directory that exceeds the standard 8.3 file name format. If <i>KeyByShortName</i> is <b>TRUE</b>, <i>LongName</i> is optional.


### -param KeyByShortName [in]

Set to <b>TRUE</b> if the file name to be deleted from the directory is the short name for the file, <b>FALSE</b> if it is the long name. 


### -param DataLength [in]

Length in bytes of the information to be stored in the tunnel cache entry for this file. The value of this parameter is file-system-specific, but it must be the same for all entries in the tunnel cache.


### -param Data [in]

Pointer to a buffer that contains file-system-specific information to be stored in the tunnel cache entry for this file.


## -returns



None




## -remarks



When a file name is removed from a directory (for a file that is being renamed or deleted), the file system can cache the file name by calling <b>FsRtlAddToTunnelCache</b>. The purpose of the tunnel cache is to propagate file properties if a new file is created that has the same long or short name as the file just deleted or renamed.

<b>FsRtlAddToTunnelCache</b> creates a new entry that contains the specified file name and directory key, and adds the entry to the tunnel cache for the mounted volume where the file is being removed or deleted. This entry can also contain a fixed-size data packet of file-system-specific information for the file. 

The caller is required to synchronize this call against <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md">FsRtlDeleteTunnelCache</a>. In other words, a file system must ensure that it does not call <b>FsRtlAddToTunnelCache</b> and <b>FsRtlDeleteTunnelCache</b> at the same time from different threads. 

For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;id=172190">Microsoft Knowledge Base Article 172190</a>.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md">FsRtlInitializeTunnelCache</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletekeyfromtunnelcache~r1.md">FsRtlDeleteKeyFromTunnelCache</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md">FsRtlDeleteTunnelCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAddToTunnelCache routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

