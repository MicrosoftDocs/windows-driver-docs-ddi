---
UID: NF:prefix.RxpAcquirePrefixTableLockShared
title: RxpAcquirePrefixTableLockShared function
author: windows-driver-content
description: RxpAcquirePrefixTableLockShared acquires the prefix table lock shared.
old-location: ifsk\rxpacquireprefixtablelockshared.htm
old-project: ifsk
ms.assetid: 89924d1d-80c2-4778-9647-c3add9e7d013
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxpAcquirePrefixTableLockShared, rxref_340b65e8-2dba-4895-8cdf-e3464d14f5a3.xml, prefix/RxpAcquirePrefixTableLockShared, RxpAcquirePrefixTableLockShared function [Installable File System Drivers], ifsk.rxpacquireprefixtablelockshared
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prefix.h
req.include-header: Prefix.h
req.target-type: Desktop
req.target-min-winverclnt: On Windows Server 2003, the RxpAcquirePrefixTableLockShared routine is implemented as a macro. This routine is only available onWindows XP and Windows 2000.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	prefix.h
apiname:
-	RxpAcquirePrefixTableLockShared
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# RxpAcquirePrefixTableLockShared function


## -description


<b>RxpAcquirePrefixTableLockShared</b> acquires the prefix table lock shared. 


## -syntax


````
BOOLEAN RxpAcquirePrefixTableLockShared(
   PRX_PREFIX_TABLE pTable,
   BOOLEAN          Wait
);
````


## -parameters




#### - pTable

A pointer to the RX_PREFIX_TABLE structure where the lock will be acquired.


#### - Wait

A Boolean value that specifies the behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, whether the shared resource can be acquired. 


### -param ProcessBufferingStateChangeRequests

TBD


### -param FileName

TBD


### -param LineNumber

TBD



## -returns


<b>RxpAcquirePrefixTableLockShared</b> returns <b>TRUE</b> if the resource is acquired. This routine returns <b>FALSE</b> if the <i>Wait</i> parameter is <b>FALSE</b> and shared access cannot be granted immediately.



## -remarks


The <b>RxAcquirePrefixTableLockShared</b> macro calls the <b>RxpAcquirePrefixTableLockShared</b> routine. The <b>RxIsPrefixTableLockAcquired</b> macro can be used to determine whether an exclusive or shared prefix table lock was previously acquired. 

Normal kernel APC delivery should be disabled before calling this routine. Normal kernel APC delivery can be disabled by calling <b>FsRtlEnterFileSystem</b> or <b>KeEnterCriticalRegion</b>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <b>FsRtlExitFileSystem</b> or <b>KeLeaveCriticalRegion</b>.



## -see-also

<a href="..\prefix\nf-prefix-rxpacquireprefixtablelockexclusive.md">RxpAcquirePrefixTableLockExclusive</a>

<a href="..\prefix\nf-prefix-rxprefixtablelookupname.md">RxPrefixTableLookupName</a>

<a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a>

<a href="..\prefix\nf-prefix-rxpreleaseprefixtablelock.md">RxpReleasePrefixTableLock</a>

<a href="..\ntddk\nf-ntddk-keleavecriticalregion.md">KeLeaveCriticalRegion</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545900">FsRtlEnterFileSystem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpAcquirePrefixTableLockShared function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

