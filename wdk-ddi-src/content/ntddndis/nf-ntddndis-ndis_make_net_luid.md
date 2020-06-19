---
UID: NF:ntddndis.NDIS_MAKE_NET_LUID
title: NDIS_MAKE_NET_LUID macro (ntddndis.h)
description: The NDIS_MAKE_NET_LUID macro builds a NET_LUID value from an interface type and a NET_LUID index.
tech.root: netvista
ms.assetid: e8f14ed7-53ed-4bef-af8c-a7f818437d98
ms.date: 04/16/2018
keywords: ["NDIS_MAKE_NET_LUID macro"]
f1_keywords:
 - "ntddndis/NDIS_MAKE_NET_LUID"
ms.keywords: NDIS_MAKE_NET_LUID
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddndis.h
api_name: 
- NDIS_MAKE_NET_LUID
product:
- Windows
targetos: Windows

---

# NDIS_MAKE_NET_LUID macro


## -description

The NDIS_MAKE_NET_LUID macro builds a [**NET_LUID**](https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh) value from an interface type and a NET_LUID index.

## -parameters

### -param _pNetLuid

A pointer to a caller-supplied [**NET_LUID**](https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh) union. **NDIS_MAKE_NET_LUID** returns the newly created NET_LUID value in this variable.

### -param _IfType

The Internet Assigned Numbers Authority (IANA) interface type. **NDIS_MAKE_NET_LUID** writes the value at *\_IfType* to the **IfType** member of the NET_LUID union that the caller provided at *\_pNetLuid* . For a list of interface types, see [NDIS Interface Types](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-interface-types).

### -param _NetLuidIndex

A NET_LUID index that the caller allocated with the [**NdisIfAllocateNetLuidIndex**](../ndis/nf-ndis-ndisifallocatenetluidindex.md) function. **NDIS_MAKE_NET_LUID** writes the value at *\_NetLuidIndex* to the **NetLuidIndex** member of the **NET_LUID** union that the caller provided at *\_pNetLuid* .

## -remarks

NDIS network interface providers should use the **NDIS_MAKE_NET_LUID** macro to build a [**NET_LUID**](https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh) value. The provider passes the resulting **NET_LUID** value to the [**NdisIfRegisterInterface**](../ndis/nf-ndis-ndisifregisterinterface.md) function to register the interface with NDIS.

## -see-also

[**NdisIfAllocateNetLuidIndex**](../ndis/nf-ndis-ndisifallocatenetluidindex.md)

[**NdisIfRegisterInterface**](../ndis/nf-ndis-ndisifregisterinterface.md)

[**NET_LUID**](https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh)
