---
UID: NS:wwan._WWAN_SET_UICC_TERMINAL_CAPABILITY
tech.root: netvista
title: WWAN_SET_UICC_TERMINAL_CAPABILITY
ms.date: 02/28/2022
targetos: Windows
description: 
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
req.target-min-winverclnt: WIN11_NEXT
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

The **WWAN_SET_UICC_TERMINAL_CAPABILITY** structure represents the SIM slot ID that is associated with an OID_WWAN_UICC_TERMINAL_CAPABILITY set request.

## -struct-fields

### -field SlotId

A ULOG value that identifies the SIM slot of the operation. For single SIM devices this value is 0. For dual SIM devices this value is [0..1].

### -field CapabilityListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) object that represents a list of terminal capability objects.

## -remarks

Is this an on off thing??
 used to inform the UICC about terminal capability. 

## -see-also

