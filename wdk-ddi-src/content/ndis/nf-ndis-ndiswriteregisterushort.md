---
UID: NF:ndis.NdisWriteRegisterUshort
title: NdisWriteRegisterUshort macro (ndis.h)
description: NdisWriteRegisterUshort is called by the miniport driver to write a USHORT to a memory-mapped device register.
old-location: netvista\ndiswriteregisterushort.htm
tech.root: netvista
ms.assetid: 676beebf-4c22-4eb5-bfad-a6f66f3a95be
ms.date: 05/02/2018
keywords: ["NdisWriteRegisterUshort macro"]
ms.keywords: NdisWriteRegisterUshort, NdisWriteRegisterUshort macro [Network Drivers Starting with Windows Vista], miniport_register_ref_a2e4ab78-aab2-4076-8f66-4e48a60b5beb.xml, ndis/NdisWriteRegisterUshort, netvista.ndiswriteregisterushort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisWriteRegisterUshort
 - ndis/NdisWriteRegisterUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisWriteRegisterUshort
---

# NdisWriteRegisterUshort macro


## -description

<b>NdisWriteRegisterUshort</b> is called by the miniport driver to write a USHORT to a memory-mapped device
  register.

## -parameters

### -param Register 

[in]
Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>.

### -param Data 

[in]
Specifies the caller-supplied USHORT that this function transfers to the 
     <i>Register</i> .

## -remarks

If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisterushort">NdisReadRegisterUshort</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisteruchar">NdisWriteRegisterUchar</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisterulong">NdisWriteRegisterUlong</a>