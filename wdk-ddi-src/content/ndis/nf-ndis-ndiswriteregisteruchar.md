---
UID: NF:ndis.NdisWriteRegisterUchar
title: NdisWriteRegisterUchar macro (ndis.h)
description: NdisWriteRegisterUchar is called by the miniport driver to write a UCHAR to a memory-mapped device register.
old-location: netvista\ndiswriteregisteruchar.htm
tech.root: netvista
ms.assetid: 8f720af6-d70a-4682-86f4-011e70a6f64f
ms.date: 05/02/2018
keywords: ["NdisWriteRegisterUchar macro"]
ms.keywords: NdisWriteRegisterUchar, NdisWriteRegisterUchar macro [Network Drivers Starting with Windows Vista], miniport_register_ref_60f684ba-a2ca-4fa8-8a80-9e805fb5c453.xml, ndis/NdisWriteRegisterUchar, netvista.ndiswriteregisteruchar
f1_keywords:
 - "ndis/NdisWriteRegisterUchar"
 - "NdisWriteRegisterUchar"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisWriteRegisterUchar
targetos: Windows
req.typenames: 
---

# NdisWriteRegisterUchar macro


## -description


<b>NdisWriteRegisterUchar</b> is called by the miniport driver to write a UCHAR to a memory-mapped device
  register.


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>.


### -param Data [in]

Specifies the caller-supplied UCHAR that this function transfers to the 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisteruchar">NdisReadRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisterulong">NdisWriteRegisterUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisterushort">NdisWriteRegisterUshort</a>
 

 

