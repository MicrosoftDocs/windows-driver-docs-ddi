---
UID: NS:wwan._WWAN_UICC_TERMINAL_CAPABILITY_INFO
tech.root: netvista
title: WWAN_UICC_TERMINAL_CAPABILITY_INFO
ms.date: 01/24/2022
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
req.typenames: WWAN_UICC_TERMINAL_CAPABILITY_INFO, *PWWAN_UICC_TERMINAL_CAPABILITY_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - PWWAN_UICC_TERMINAL_CAPABILITY_INFO
 - WWAN_UICC_TERMINAL_CAPABILITY_INFO
f1_keywords:
 - _WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - wwan/_WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - PWWAN_UICC_TERMINAL_CAPABILITY_INFO
 - wwan/PWWAN_UICC_TERMINAL_CAPABILITY_INFO
 - WWAN_UICC_TERMINAL_CAPABILITY_INFO
 - wwan/WWAN_UICC_TERMINAL_CAPABILITY_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_UICC_TERMINAL_CAPABILITY_INFO
---

## -description

The **WWAN_UICC_TERMINAL_CAPABILITY_INFO** structure contains information about the capabilities of the host. 

## -struct-fields

### -field CapabilityListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) structure that represents a list of SAR configurations that the modem supports. The **ElementType** member in the **WWAN_LIST_HEADER** should be set to **WwanStructSarConfig**. The **ElementCount** member in the **WWAN_LIST_HEADER** should be set to the number of SAR configurations that follow the **WWAN_LIST_HEADER** structure.

a list of UIC terminal capabilitiy?

## -remarks

## -see-also

