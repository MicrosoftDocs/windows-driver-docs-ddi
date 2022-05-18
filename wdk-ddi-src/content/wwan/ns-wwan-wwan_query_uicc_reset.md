---
UID: NS:wwan._WWAN_QUERY_UICC_RESET
tech.root: netvista
title: WWAN_QUERY_UICC_RESET
ms.date: 03/10/2022
targetos: Windows
description: The WWAN_QUERY_UICC_RESET structure represents the SIM slot ID that is associated with an OID_WWAN_UICC_RESET query request.
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
req.typenames: WWAN_QUERY_UICC_RESET, *PWWAN_QUERY_UICC_RESET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_QUERY_UICC_RESET
 - PWWAN_QUERY_UICC_RESET
 - WWAN_QUERY_UICC_RESET
f1_keywords:
 - _WWAN_QUERY_UICC_RESET
 - wwan/_WWAN_QUERY_UICC_RESET
 - PWWAN_QUERY_UICC_RESET
 - wwan/PWWAN_QUERY_UICC_RESET
 - WWAN_QUERY_UICC_RESET
 - wwan/WWAN_QUERY_UICC_RESET
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_QUERY_UICC_RESET
---

## -description

The **WWAN_QUERY_UICC_RESET** structure represents the SIM slot ID that is associated with an [OID_WWAN_UICC_RESET](/windows-hardware/drivers/network/oid-wwan-uicc-reset) query request.

## -struct-fields

### -field SlotId

A ULONG value that specifies the intended SIM slot of the operation. For a single SIM device, this value is 0. For a dual SIM device, this value is [0..1].

## -remarks

## -see-also

[OID_WWAN_UICC_RESET](/windows-hardware/drivers/network/oid-wwan-uicc-reset)