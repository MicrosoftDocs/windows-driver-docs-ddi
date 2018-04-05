---
UID: NF:prefix.RxpAcquirePrefixTableLockExclusive
title: RxpAcquirePrefixTableLockExclusive function
author: windows-driver-content
description: RxpAcquirePrefixTableLockExclusive acquires the prefix table lock exclusively.
old-location: ifsk\rxpacquireprefixtablelockexclusive.htm
old-project: ifsk
ms.assetid: 62f0bfd3-b8d9-4b29-a811-91a6c66dc24f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxpAcquirePrefixTableLockExclusive, RxpAcquirePrefixTableLockExclusive function [Installable File System Drivers], ifsk.rxpacquireprefixtablelockexclusive, prefix/RxpAcquirePrefixTableLockExclusive, rxref_3e3f34a4-ccc4-434b-9df0-b320923178d3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prefix.h
req.include-header: Prefix.h
req.target-type: Desktop
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
-	RxpAcquirePrefixTableLockExclusive
product:
- Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# RxpAcquirePrefixTableLockExclusive function


## -description


<b>RxpAcquirePrefixTableLockExclusive</b> acquires the prefix table lock exclusively. 


## -parameters




### -param pTable

A pointer to the RX_PREFIX_TABLE where the lock will be acquired.


### -param Wait

A Boolean value that specifies the behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, whether the resource can be acquired. 


### -param ProcessBufferingStateChangeRequests

TBD


### -param FileName

TBD


### -param LineNumber

TBD




## -returns



<b>RxpAcquirePrefixTableLockExclusive</b> returns <b>TRUE</b> if the resource is acquired. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and exclusive access cannot be granted immediately.




## -remarks



The <b>RxAcquirePrefixTableLockExclusive</b> routine is implemented as a macro on Windows Server 2003. On Windows XP and Windows 2000, <b>RxAcquirePrefixTableLockExclusive </b>is implemented as a routine. 

The <b>RxAcquirePrefixTableLockExclusive</b> macro calls the  <b>RxpAcquirePrefixTableLockExclusive</b> routine. The <b>RxIsPrefixTableLockExclusive</b> macro can be used to determine if an exclusive prefix table lock was previously acquired. The <b>RxIsPrefixTableLockAcquired</b> macro can also be used to determine if either an exclusive or shared prefix table lock was previously acquired. 

Normal kernel APC delivery should be disabled before calling this routine. Disable normal kernel APC delivery by calling <b>FsRtlEnterFileSystem</b> or <b>KeEnterCriticalRegion</b>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <b>FsRtlExitFileSystem</b> or <b>KeLeaveCriticalRegion</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545900">FsRtlEnterFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554632">RxPrefixTableLookupName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554598">RxpAcquirePrefixTableLockShared</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554637">RxpReleasePrefixTableLock</a>
 

 

