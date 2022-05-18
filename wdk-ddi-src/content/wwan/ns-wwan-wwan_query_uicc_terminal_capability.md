---
UID: NS:wwan._WWAN_QUERY_UICC_TERMINAL_CAPABILITY
tech.root: netvista
title: WWAN_QUERY_UICC_TERMINAL_CAPABILITY
ms.date: 03/10/2022
targetos: Windows
description: The WWAN_QUERY_UICC_TERMINAL_CAPABILITY structure represents the SIM slot ID that is associated with an OID_WWAN_UICC_TERMINAL_CAPABILITY query request.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_QUERY_UICC_TERMINAL_CAPABILITY, *PWWAN_QUERY_UICC_TERMINAL_CAPABILITY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - PWWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - WWAN_QUERY_UICC_TERMINAL_CAPABILITY
f1_keywords:
 - _WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - wwan/_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - PWWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - wwan/PWWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - wwan/WWAN_QUERY_UICC_TERMINAL_CAPABILITY
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_QUERY_UICC_TERMINAL_CAPABILITY
---

## -description

The **WWAN_QUERY_UICC_TERMINAL_CAPABILITY** structure represents the SIM slot ID that is associated with an [OID_WWAN_UICC_TERMINAL_CAPABILITY](/windows-hardware/drivers/network/oid-wwan-uicc-terminal-capability) query request.

## -struct-fields

### -field SlotId

A ULONG value that specifies the intended SIM slot of the operation. For a single SIM device, this value is 0. For a dual SIM device, this value is [0..1].

## -remarks

## -see-also

[OID_WWAN_UICC_TERMINAL_CAPABILITY](/windows-hardware/drivers/network/oid-wwan-uicc-terminal-capability)

[**NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY**](../ndiswwan/ns-ndiswwan-ndis_wwan_query_uicc_terminal_capability.md)