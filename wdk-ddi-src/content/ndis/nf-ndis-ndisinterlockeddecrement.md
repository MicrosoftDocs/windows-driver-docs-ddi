---
UID: NF:ndis.NdisInterlockedDecrement
title: NdisInterlockedDecrement macro
author: windows-driver-content
description: The NdisInterlockedDecrement function decrements a caller-supplied variable of type LONG as an atomic operation.
old-location: netvista\ndisinterlockeddecrement.htm
old-project: netvista
ms.assetid: cf425cd6-88e6-479f-a5c7-364ae896145d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisInterlockedDecrement, NdisInterlockedDecrement macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedDecrement, ndis_interlocked_ref_bbf1ad9d-0f18-4746-9fa3-b2b2c4101a41.xml, netvista.ndisinterlockeddecrement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInterlockedDecrement (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInterlockedDecrement (NDIS   5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInterlockedDecrement
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInterlockedDecrement macro


## -description


The 
  <b>NdisInterlockedDecrement</b> function decrements a caller-supplied variable of type LONG as an atomic
  operation.


## -syntax


````
LONG NdisInterlockedDecrement(
  [in] PLONG Addend
);
````


## -parameters




### -param Addend [in]

A pointer to the variable to be decremented.


## -remarks



<b>NdisInterlockedDecrement</b> can safely be used on variables in pageable memory.

<b>NdisInterlockedDecrement</b> is atomic only with respect to other 
    <b>NdisInterlocked<i>Xxx</i></b> calls.




## -see-also

<a href="..\ndis\nf-ndis-ndisinterlockedincrement.md">NdisInterlockedIncrement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedDecrement macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

