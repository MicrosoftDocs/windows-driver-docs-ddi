---
UID: NF:ntifs.MmPrefetchPages
title: MmPrefetchPages function
author: windows-driver-content
description: The MmPrefetchPages routine reads groups of pages from secondary storage in the optimal fashion.
old-location: ifsk\mmprefetchpages.htm
old-project: ifsk
ms.assetid: fd76dfed-2c47-4289-a672-1db8129f5a9e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: MmPrefetchPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmPrefetchPages
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# MmPrefetchPages function



## -description
The <b>MmPrefetchPages</b> routine reads groups of pages from secondary storage in the optimal fashion. 



## -syntax

````
NTSTATUS MmPrefetchPages(
  _In_ ULONG      NumberOfLists,
  _In_ PREAD_LIST *ReadLists
);
````


## -parameters

### -param NumberOfLists [in]

The number of read-lists in the array passed in the <i>ReadLists</i> parameter.


### -param ReadLists [in]

A pointer to an array of read-lists to be prefetched.


## -returns
<b>MmPrefetchPages</b> returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A temporary buffer required by this function could not be allocated. 

 

<b>MmPrefetchPages</b> returns STATUS_SUCCESS on success and also if all of the requested pages were already in memory indicating no reads from secondary storage were required. 


## -remarks
<b>MmPrefetchPages</b> reads pages from secondary storage described in the read-lists in the optimal fashion. The caller builds a list of various file objects and logical block offsets, passing them to the <b>MmPrefetchPages</b> function which examines the internal pages, reading in those that are not already valid or in transition. The pages are read with a single read, using a dummy page to bridge small gaps. If the gap is "large", then separate reads are issued. </p>