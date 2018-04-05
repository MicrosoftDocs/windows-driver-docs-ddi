---
UID: NF:ndis.NdisWriteRegisterUchar
title: NdisWriteRegisterUchar macro
author: windows-driver-content
description: NdisWriteRegisterUchar is called by the miniport driver to write a UCHAR to a memory-mapped device register.
old-location: netvista\ndiswriteregisteruchar.htm
old-project: netvista
ms.assetid: 8f720af6-d70a-4682-86f4-011e70a6f64f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisWriteRegisterUchar, NdisWriteRegisterUchar macro [Network Drivers Starting with Windows Vista], miniport_register_ref_60f684ba-a2ca-4fa8-8a80-9e805fb5c453.xml, ndis/NdisWriteRegisterUchar, netvista.ndiswriteregisteruchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUchar (NDIS   5.1)) in Windows XP.
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisWriteRegisterUchar
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisWriteRegisterUchar macro


## -description


<b>NdisWriteRegisterUchar</b> is called by the miniport driver to write a UCHAR to a memory-mapped device
  register.


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.


### -param Data [in]

Specifies the caller-supplied UCHAR that this function transfers to the 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564513">NdisReadRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564683">NdisWriteRegisterUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564685">NdisWriteRegisterUshort</a>
 

 

