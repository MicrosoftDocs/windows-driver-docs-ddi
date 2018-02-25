---
UID: NF:ntifs.CcGetFileObjectFromBcb
title: CcGetFileObjectFromBcb function
author: windows-driver-content
description: Given a pointer to a pinned buffer control block (BCB) for a file, the CcGetFileObjectFromBcb routine returns a pointer to the file object that the cache manager is using for that file.
old-location: ifsk\ccgetfileobjectfrombcb.htm
old-project: ifsk
ms.assetid: d30a2ee4-4736-4127-95db-b86e782c3577
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, C, CcGetFileObjectFromBcb, CcGetFileObjectFromBcb routine [Installable File System Drivers], F, G, O, b, c, ccref_7fdf1d1e-a080-4322-a09c-be0a16543050.xml, e, i, ifsk.ccgetfileobjectfrombcb, j, l, m, ntifs/CcGetFileObjectFromBcb, o, r, t"
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
-	CcGetFileObjectFromBcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcGetFileObjectFromBcb function


## -description


Given a pointer to a pinned buffer control block (BCB) for a file, the <b>CcGetFileObjectFromBcb</b> routine returns a pointer to the file object that the cache manager is using for that file.


## -syntax


````
PFILE_OBJECT CcGetFileObjectFromBcb(
  _In_ PVOID Bcb
);
````


## -parameters




### -param Bcb [in]

Pointer to the pinned BCB.


## -returns



Pointer to the file object, or <b>NULL</b> if the file is not cached or is no longer cached.




## -remarks



The file object pointer is guaranteed to remain valid as long as the BCB exists.




## -see-also

<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>



<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>



<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>



<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetFileObjectFromBcb routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

