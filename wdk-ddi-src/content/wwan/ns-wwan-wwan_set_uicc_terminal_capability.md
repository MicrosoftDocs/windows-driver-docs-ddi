---
UID: NS:wwan._WWAN_SET_UICC_TERMINAL_CAPABILITY
tech.root: netvista
title: WWAN_SET_UICC_TERMINAL_CAPABILITY
ms.date: 03/10/2022
targetos: Windows
description: The WWAN_SET_UICC_TERMINAL_CAPABILITY structure represents the terminal capabilities of the host and SIM slot ID associated with an OID_WWAN_UICC_TERMINAL_CAPABILITY set request.
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
req.typenames: WWAN_SET_UICC_TERMINAL_CAPABILITY, *PWWAN_SET_UICC_TERMINAL_CAPABILITY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SET_UICC_TERMINAL_CAPABILITY
 - PWWAN_SET_UICC_TERMINAL_CAPABILITY
 - WWAN_SET_UICC_TERMINAL_CAPABILITY
f1_keywords:
 - _WWAN_SET_UICC_TERMINAL_CAPABILITY
 - wwan/_WWAN_SET_UICC_TERMINAL_CAPABILITY
 - PWWAN_SET_UICC_TERMINAL_CAPABILITY
 - wwan/PWWAN_SET_UICC_TERMINAL_CAPABILITY
 - WWAN_SET_UICC_TERMINAL_CAPABILITY
 - wwan/WWAN_SET_UICC_TERMINAL_CAPABILITY
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_SET_UICC_TERMINAL_CAPABILITY
---

## -description

The **WWAN_SET_UICC_TERMINAL_CAPABILITY** structure represents the terminal capabilities of the host and SIM slot ID associated with an [OID_WWAN_UICC_TERMINAL_CAPABILITY](/windows-hardware/drivers/network/oid-wwan-uicc-terminal-capability) set request.

## -struct-fields

### -field SlotId

A ULONG value that identifies the SIM slot of the operation. For single SIM devices this value is 0. For dual SIM devices this value is [0..1].

### -field CapabilityListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) object that represents a list of terminal capability objects.

## -remarks

## -see-also

[OID_WWAN_UICC_TERMINAL_CAPABILITY](/windows-hardware/drivers/network/oid-wwan-uicc-terminal-capability)

[NDIS_STATUS_WWAN_UICC_TERMINAL_CAPABILITY_INFO](/windows-hardware/drivers/network/ndis-status-wwan-uicc-terminal-capability-info)
