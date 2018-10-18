---
UID: NF:ndis.NdisReadRegisterUshort
title: NdisReadRegisterUshort macro
author: windows-driver-content
description: NdisReadRegisterUshort is called by the miniport driver to read a USHORT from a memory-mapped device register.
old-location: netvista\ndisreadregisterushort.htm
tech.root: netvista
ms.assetid: 0048fb18-8728-4b41-b4e2-5762966d5ed0
ms.date: 05/02/2018
ms.keywords: NdisReadRegisterUshort, NdisReadRegisterUshort macro [Network Drivers Starting with Windows Vista], miniport_register_ref_7eef891a-3f3e-4c42-8165-399555eb018f.xml, ndis/NdisReadRegisterUshort, netvista.ndisreadregisterushort
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows XP.
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
-	NdisReadRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReadRegisterUshort macro


## -description


<b>NdisReadRegisterUshort</b> is called by the miniport driver to read a USHORT from a memory-mapped device
  register.


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.


### -param Data [out]

Pointer to the caller-supplied variable in which this function returns the USHORT read from 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564513">NdisReadRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564514">NdisReadRegisterUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564685">NdisWriteRegisterUshort</a>
 

 

