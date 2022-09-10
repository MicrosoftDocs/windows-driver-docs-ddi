---
UID: NS:wwan._WWAN_QUERY_READY_INFO
tech.root: netvista
title: WWAN_QUERY_READY_INFO
ms.date: 02/22/2022
targetos: Windows
description: The WWAN_QUERY_READY_INFO structure represents the SIM slot ID for OID_WWAN_READY_INFO query requests.
prerelease: false
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
req.typenames: WWAN_QUERY_READY_INFO, *PWWAN_QUERY_READY_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_QUERY_READY_INFO
 - PWWAN_QUERY_READY_INFO
 - WWAN_QUERY_READY_INFO
f1_keywords:
 - _WWAN_QUERY_READY_INFO
 - wwan/_WWAN_QUERY_READY_INFO
 - PWWAN_QUERY_READY_INFO
 - wwan/PWWAN_QUERY_READY_INFO
 - WWAN_QUERY_READY_INFO
 - wwan/WWAN_QUERY_READY_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_QUERY_READY_INFO
---

## -description

The **WWAN_QUERY_READY_INFO** structure represents the SIM slot ID that is associated with an [OID_WWAN_READY_INFO](/windows-hardware/drivers/network/oid-wwan-ready-info) query request.


## -struct-fields

### -field SlotId

A ULONG value that specifies the intended SIM slot of the operation. For single SIM device, this value is 0. For a dual SIM device, this value is [0..1].

## -remarks

## -see-also

[**NDIS_WWAN_QUERY_READY_INFO**](../ndiswwan/ns-ndiswwan-ndis_wwan_query_ready_info.md)

[OID_WWAN_READY_INFO](/windows-hardware/drivers/network/oid-wwan-ready-info)