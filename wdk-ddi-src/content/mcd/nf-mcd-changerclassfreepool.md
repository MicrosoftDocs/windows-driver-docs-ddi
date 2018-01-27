---
UID: NF:mcd.ChangerClassFreePool
title: ChangerClassFreePool function
author: windows-driver-content
description: The ChangerClassFreePool routine frees pool memory previously allocated using ChangerClassAllocatePool.
old-location: storage\changerclassfreepool.htm
old-project: storage
ms.assetid: c20c39f9-ceee-47f0-849a-f8686fb05e6a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mcd/ChangerClassFreePool, storage.changerclassfreepool, chgrclas_3f5fb8a4-3c85-4dde-80c9-f8e001b7b3bd.xml, ChangerClassFreePool, ChangerClassFreePool routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Mcd.lib
-	Mcd.dll
apiname: 
-	ChangerClassFreePool
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerClassFreePool function


## -description


The <b>ChangerClassFreePool</b> routine frees pool memory previously allocated using <a href="..\mcd\nf-mcd-changerclassallocatepool.md">ChangerClassAllocatePool</a>. 


## -syntax


````
VOID ChangerClassFreePool(
  _In_ PVOID PoolToFree
);
````


## -parameters




### -param PoolToFree [in]

Pointer to the block of memory to be freed.


## -returns


None



## -see-also

<a href="..\mcd\nf-mcd-changerclassallocatepool.md">ChangerClassAllocatePool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerClassFreePool routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

