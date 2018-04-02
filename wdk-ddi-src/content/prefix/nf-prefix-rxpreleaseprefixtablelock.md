---
UID: NF:prefix.RxpReleasePrefixTableLock
title: RxpReleasePrefixTableLock function
author: windows-driver-content
description: RxpReleasePrefixTableLock releases a previously acquired shared or exclusive prefix table lock.
old-location: ifsk\rxpreleaseprefixtablelock.htm
old-project: ifsk
ms.assetid: 57aef4ed-2ece-4af3-b1ca-e4fe5a306f82
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxpReleasePrefixTableLock, RxpReleasePrefixTableLock function [Installable File System Drivers], ifsk.rxpreleaseprefixtablelock, prefix/RxpReleasePrefixTableLock, rxref_34f5b33a-efeb-42a0-8e57-6c32c262319a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prefix.h
req.include-header: Prefix.h
req.target-type: Desktop
req.target-min-winverclnt: RxpReleasePrefixTableLock routine is only available on Windows XP and Windows 2000.
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	prefix.h
api_name:
-	RxpReleasePrefixTableLock
product:
- Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# RxpReleasePrefixTableLock function


## -description


<b>RxpReleasePrefixTableLock</b> releases a previously acquired shared or exclusive prefix table lock. 


## -parameters




### -param pTable

A pointer to the RX_PREFIX_TABLE structure where the lock was previously acquired.


### -param ProcessBufferingStateChangeRequests

TBD


### -param FileName

TBD


### -param LineNumber

TBD




## -returns



None




## -remarks



On Windows Server 2003, this routine is implemented as a macro. The <b>RxReleasePrefixTableLock</b> macro can be used to call this routine. 

Normal kernel APC delivery should be disabled before calling the <b>RxpAcquirePrefixTableLockExclusive</b> or <b>RxpAcquirePrefixTableLockShared</b> routines to acquire the lock. Normal kernel APC delivery can be disabled by calling <b>FsRtlEnterFileSystem</b> or <b>KeEnterCriticalRegion</b>. Delivery must remain disabled until the resource is released by calling <b>RxpReleasePrefixTableLock</b>, at which point it can be reenabled by calling <b>FsRtlExitFileSystem</b> or <b>KeLeaveCriticalRegion</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545900">FsRtlEnterFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554632">RxPrefixTableLookupName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554595">RxpAcquirePrefixTableLockExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554598">RxpAcquirePrefixTableLockShared</a>
 

 

