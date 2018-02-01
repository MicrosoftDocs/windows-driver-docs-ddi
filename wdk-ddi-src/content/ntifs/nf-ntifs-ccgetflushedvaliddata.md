---
UID: NF:ntifs.CcGetFlushedValidData
title: CcGetFlushedValidData function
author: windows-driver-content
description: The CcGetFlushedValidData routine determines how much of a cached file has been flushed to disk.
old-location: ifsk\ccgetflushedvaliddata.htm
old-project: ifsk
ms.assetid: a0e3700a-768f-4025-b5f2-715e25e1d10d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ccref_021f04d4-537c-49a3-bfac-8eeea908c100.xml, ntifs/CcGetFlushedValidData, ifsk.ccgetflushedvaliddata, CcGetFlushedValidData routine [Installable File System Drivers], CcGetFlushedValidData
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcGetFlushedValidData
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcGetFlushedValidData function


## -description


The <b>CcGetFlushedValidData</b> routine determines how much of a cached file has been flushed to disk.


## -syntax


````
LARGE_INTEGER CcGetFlushedValidData(
  _In_ PSECTION_OBJECT_POINTERS SectionObjectPointer,
  _In_ BOOLEAN                  BcbListHeld
);
````


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

<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>

<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetFlushedValidData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

