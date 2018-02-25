---
UID: NF:ntifs.CcIsThereDirtyData
title: CcIsThereDirtyData function
author: windows-driver-content
description: The CcIsThereDirtyData routine determines whether a mounted volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydata.htm
old-project: ifsk
ms.assetid: 592c7f8d-0a39-45af-a9b8-14ddd55e2835
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, CcIsThereDirtyData, CcIsThereDirtyData routine [Installable File System Drivers], D, I, T, a, c, ccref_86c4a327-a13e-49b3-89d1-abf976973000.xml, e, h, i, ifsk.ccistheredirtydata, ntifs/CcIsThereDirtyData, r, s, t, y"
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcIsThereDirtyData
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcIsThereDirtyData function


## -description


The <b>CcIsThereDirtyData</b> routine determines whether a mounted volume contains any files that have dirty data in the system cache.


## -syntax


````
BOOLEAN CcIsThereDirtyData(
  _In_ PVPB Vpb
);
````


## -parameters




### -param Vpb [in]

Pointer to a volume parameter block (VPB) for the volume.


## -returns



<b>CcIsThereDirtyData</b> returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache but not yet flushed to disk, <b>FALSE</b> otherwise.




## -remarks



<b>CcIsThereDirtyData</b> ignores temporary files.




## -see-also

<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>



<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcIsThereDirtyData routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

