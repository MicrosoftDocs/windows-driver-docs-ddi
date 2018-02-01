---
UID: NF:wdm.ExReinitializeResourceLite
title: ExReinitializeResourceLite function
author: windows-driver-content
description: The ExReinitializeResourceLite routine reinitializes an existing resource variable.
old-location: kernel\exreinitializeresourcelite.htm
old-project: kernel
ms.assetid: 5713edfd-0b73-4274-862d-23c97f991a68
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExReinitializeResourceLite routine [Kernel-Mode Driver Architecture], kernel.exreinitializeresourcelite, ExReinitializeResourceLite, k102_dc743b18-db19-4536-a862-e313e201d4d8.xml, wdm/ExReinitializeResourceLite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExReinitializeResourceLite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReinitializeResourceLite function


## -description


The <b>ExReinitializeResourceLite</b> routine reinitializes an existing resource variable.


## -syntax


````
NTSTATUS ExReinitializeResourceLite(
  _Inout_ PERESOURCE Resource
);
````


## -parameters




### -param Resource [in, out]

A pointer to the caller-supplied resource variable to be reinitialized.


## -returns


<b>ExReinitializeResourceLite</b> returns STATUS_SUCCESS.



## -remarks


With a single call to <b>ExReinitializeResource</b>, a driver writer can replace three calls: one to <b>ExDeleteResourceLite</b>, another to <b>ExAllocatePool</b>, and a third to <b>ExInitializeResourceLite</b>. As contention for a resource variable increases, memory is dynamically allocated and attached to the resource in order to track this contention. As an optimization, <b>ExReinitializeResourceLite</b> retains and zeros this previously allocated memory.

The <b>ERESOURCE</b> structure is opaque; that is, the members are reserved for system use.



## -see-also

<a href="..\wdm\nf-wdm-exacquiresharedstarveexclusive.md">ExAcquireSharedStarveExclusive</a>

<a href="..\wdm\nf-wdm-exacquiresharedwaitforexclusive.md">ExAcquireSharedWaitForExclusive</a>

<a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a>

<a href="..\wdm\nf-wdm-exisresourceacquiredsharedlite.md">ExIsResourceAcquiredSharedLite</a>

<a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>

<a href="..\wdm\nf-wdm-exacquireresourceexclusivelite.md">ExAcquireResourceExclusiveLite</a>

<a href="..\wdm\nf-wdm-exconvertexclusivetosharedlite.md">ExConvertExclusiveToSharedLite</a>

<a href="..\wdm\nf-wdm-exisresourceacquiredexclusivelite.md">ExIsResourceAcquiredExclusiveLite</a>

<a href="..\wdm\nf-wdm-exdeleteresourcelite.md">ExDeleteResourceLite</a>

<a href="..\wdm\nf-wdm-exinitializeresourcelite.md">ExInitializeResourceLite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExReinitializeResourceLite routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

