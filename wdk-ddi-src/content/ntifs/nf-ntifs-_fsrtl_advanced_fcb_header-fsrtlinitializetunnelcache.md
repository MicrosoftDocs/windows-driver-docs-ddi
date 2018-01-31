---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeTunnelCache
title: FsRtlInitializeTunnelCache function
author: windows-driver-content
description: The FsRtlInitializeTunnelCache routine initializes a new tunnel cache for a volume.
old-location: ifsk\fsrtlinitializetunnelcache.htm
old-project: ifsk
ms.assetid: c499c11f-1de5-4c7f-aa26-62d2221c35bd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fsrtlinitializetunnelcache, ntifs/FsRtlInitializeTunnelCache, fsrtlref_33e2bd32-4b53-4edc-8e61-7a0ffbab327a.xml, FsRtlInitializeTunnelCache, FsRtlInitializeTunnelCache routine [Installable File System Drivers]
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
-	FsRtlInitializeTunnelCache
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlInitializeTunnelCache function


## -description


The <b>FsRtlInitializeTunnelCache</b> routine initializes a new tunnel cache for a volume.


## -syntax


````
VOID FsRtlInitializeTunnelCache(
  _In_ TUNNEL *Cache
);
````


## -parameters




#### - Cache [in]

Pointer to a per-volume TUNNEL structure for which the caller must provide resident storage in nonpaged pool. 


## -returns


None



## -remarks


<b>FsRtlInitializeTunnelCache</b> initializes a new tunnel cache. File systems must call <b>FsRtlInitializeTunnelCache</b> before using any other <b>FsRtl...TunnelCache</b> routines on the tunnel cache.

File systems can use a per-volume tunnel cache to cache file names and other metadata for files that are being renamed or deleted. 

Entries are added to the tunnel cache by calling <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdtotunnelcache~r6.md">FsRtlAddToTunnelCache</a>. Each entry contains the file name and directory key for a file, and can also contain a fixed-size data packet of file-system-specific information. When the tunnel cache becomes full, older entries are removed automatically. 

For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;id=172190">Microsoft Knowledge Base Article 172190</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdtotunnelcache~r6.md">FsRtlAddToTunnelCache</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitializeTunnelCache routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

