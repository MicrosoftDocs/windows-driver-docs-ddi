---
UID: NF:ndis.NdisReadRegisterUlong
title: NdisReadRegisterUlong macro (ndis.h)
description: NdisReadRegisterUlong is called by the miniport driver to read a ULONG from a memory-mapped device register.
old-location: netvista\ndisreadregisterulong.htm
tech.root: netvista
ms.assetid: 18812c18-ec5e-4e8e-9ecf-c3c2a58ca8a2
ms.date: 05/02/2018
ms.keywords: NdisReadRegisterUlong, NdisReadRegisterUlong macro [Network Drivers Starting with Windows Vista], miniport_register_ref_44b40f81-b21f-4b5c-b875-deb9b4bd62ab.xml, ndis/NdisReadRegisterUlong, netvista.ndisreadregisterulong
ms.topic: macro
f1_keywords:
 - "ndis/NdisReadRegisterUlong"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUlong (NDIS   5.1)) in Windows XP.
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
- NdisReadRegisterUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReadRegisterUlong macro


## -description


<b>NdisReadRegisterUlong</b> is called by the miniport driver to read a ULONG from a memory-mapped device
  register.


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>.


### -param Data [out]

Pointer to the caller-supplied variable in which this function returns the ULONG read from 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisteruchar">NdisReadRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisterushort">NdisReadRegisterUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisterulong">NdisWriteRegisterUlong</a>
 

 

