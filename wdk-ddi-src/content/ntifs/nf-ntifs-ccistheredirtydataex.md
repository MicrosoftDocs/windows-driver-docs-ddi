---
UID: NF:ntifs.CcIsThereDirtyDataEx
title: CcIsThereDirtyDataEx function
author: windows-driver-content
description: The CcIsThereDirtyDataEx routine determines whether a volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydataex.htm
old-project: ifsk
ms.assetid: 88378f82-2975-4b53-9dde-53ab81df3c53
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcIsThereDirtyDataEx, CcIsThereDirtyDataEx routine [Installable File System Drivers], ccref_13ae1f3e-b2ea-4bc6-a1cb-0101afd58d04.xml, ifsk.ccistheredirtydataex, ntifs/CcIsThereDirtyDataEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcIsThereDirtyDataEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcIsThereDirtyDataEx function


## -description


The <b>CcIsThereDirtyDataEx</b> routine determines whether a volume contains any files that have dirty data in the system cache.


## -syntax


````
BOOLEAN CcIsThereDirtyDataEx(
  _In_     PVPB   Vpb,
  _In_opt_ PULONG NumberOfDirtyPages
);
````


## -parameters




### -param Vpb [in]

A pointer to a volume parameter block (VPB) for the volume. 


### -param NumberOfDirtyPages [in, optional]

An optional pointer to an unsigned long buffer that receives the number of dirty pages on the volume (associated with the Vpb parameter). 


## -returns



The <b>CcIsThereDirtyDataEx</b> routine returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache, but not yet flushed to disk. Otherwise, this routine returns <b>FALSE</b>.




## -remarks



This routine will return <b>TRUE</b> if any dirty pages exist including temporary files (<a href="..\ntifs\nf-ntifs-ccistheredirtydata.md">CcIsThereDirtyData</a> ignores temporary files).  It will also return <b>TRUE</b> if there is any data currently queued to the volume.




## -see-also

<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>



<a href="..\ntifs\nf-ntifs-ccistheredirtydata.md">CcIsThereDirtyData</a>



<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcIsThereDirtyDataEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

