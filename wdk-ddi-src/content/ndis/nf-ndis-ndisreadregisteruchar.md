---
UID: NF:ndis.NdisReadRegisterUchar
title: NdisReadRegisterUchar macro (ndis.h)
description: NdisReadRegisterUchar is called by the miniport driver to read a UCHAR from a memory-mapped device register.
old-location: netvista\ndisreadregisteruchar.htm
tech.root: netvista
ms.assetid: 1723672b-aff7-49ca-a027-14a6eb3c2196
ms.date: 05/02/2018
keywords: ["NdisReadRegisterUchar macro"]
ms.keywords: NdisReadRegisterUchar, NdisReadRegisterUchar macro [Network Drivers Starting with Windows Vista], miniport_register_ref_04023727-eaf7-45fb-b70d-5a67eda4a54d.xml, ndis/NdisReadRegisterUchar, netvista.ndisreadregisteruchar
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows XP.
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
 - NdisReadRegisterUchar
 - ndis/NdisReadRegisterUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisReadRegisterUchar
---

# NdisReadRegisterUchar macro


## -description

<b>NdisReadRegisterUchar</b> is called by the miniport driver to read a UCHAR from a memory-mapped device
  register.

## -parameters

### -param Register 

[in]
Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>.

### -param Data 

[out]
Pointer to the caller-supplied variable in which this function returns the UCHAR read from 
     <i>Register</i> .

## -remarks

If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisterulong">NdisReadRegisterUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadregisterushort">NdisReadRegisterUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteregisteruchar">NdisWriteRegisterUchar</a>

