---
UID: NF:ndis.NdisWriteRegisterUshort
title: NdisWriteRegisterUshort macro
description: NdisWriteRegisterUshort is called by the miniport driver to write a USHORT to a memory-mapped device register.
old-location: netvista\ndiswriteregisterushort.htm
tech.root: netvista
ms.assetid: 676beebf-4c22-4eb5-bfad-a6f66f3a95be
ms.date: 05/02/2018
ms.keywords: NdisWriteRegisterUshort, NdisWriteRegisterUshort macro [Network Drivers Starting with Windows Vista], miniport_register_ref_a2e4ab78-aab2-4076-8f66-4e48a60b5beb.xml, ndis/NdisWriteRegisterUshort, netvista.ndiswriteregisterushort
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUshort (NDIS   5.1)) in Windows XP.
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
-	NdisWriteRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisWriteRegisterUshort macro


## -description


<b>NdisWriteRegisterUshort</b> is called by the miniport driver to write a USHORT to a memory-mapped device
  register.


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.


### -param Data [in]

Specifies the caller-supplied USHORT that this function transfers to the 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564515">NdisReadRegisterUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564678">NdisWriteRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564683">NdisWriteRegisterUlong</a>
 

 

