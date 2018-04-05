---
UID: NF:ntifs.CcGetFlushedValidData
title: CcGetFlushedValidData function
author: windows-driver-content
description: The CcGetFlushedValidData routine determines how much of a cached file has been flushed to disk.
old-location: ifsk\ccgetflushedvaliddata.htm
old-project: ifsk
ms.assetid: a0e3700a-768f-4025-b5f2-715e25e1d10d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcGetFlushedValidData, CcGetFlushedValidData routine [Installable File System Drivers], ccref_021f04d4-537c-49a3-bfac-8eeea908c100.xml, ifsk.ccgetflushedvaliddata, ntifs/CcGetFlushedValidData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcGetFlushedValidData
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcGetFlushedValidData function


## -description


The <b>CcGetFlushedValidData</b> routine determines how much of a cached file has been flushed to disk.


## -parameters




### -param SectionObjectPointer [in]

Pointer to a structure containing the file object's section object pointers.


### -param BcbListHeld [in]

Reserved for system use. Must be <b>FALSE</b>.


## -returns



If the entire file has been flushed, <b>CcGetFlushedValidData</b> returns the valid data length for the file. If there are dirty pages that have not been flushed to disk, <b>CcGetFlushedValidData</b> returns the starting byte offset of the lowest dirty page currently in the file. If the file is not cached or is no longer cached, MAXLONGLONG is returned in the quad part.




## -remarks



The file system is responsible for ensuring that the value of <i>SectionObjectPointer</i> remains valid while in use. It is impossible for the cache manager to guarantee this.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>
 

 

