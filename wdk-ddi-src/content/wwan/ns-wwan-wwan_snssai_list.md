---
UID: NS:wwan._WWAN_SNSSAI_LIST
tech.root: netvista
title: WWAN_SNSSAI_LIST
ms.date: 01/14/2022
targetos: Windows
description: The WWAN_SNSSAI_LIST structure represents a single Network Slice Selection Assistance Information (S-NSSAI) list.
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
req.typenames: WWAN_SNSSAI_LIST, *PWWAN_SNSSAI_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SNSSAI_LIST
 - PWWAN_SNSSAI_LIST
 - WWAN_SNSSAI_LIST
f1_keywords:
 - _WWAN_SNSSAI_LIST
 - wwan/_WWAN_SNSSAI_LIST
 - PWWAN_SNSSAI_LIST
 - wwan/PWWAN_SNSSAI_LIST
 - WWAN_SNSSAI_LIST
 - wwan/WWAN_SNSSAI_LIST
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_SNSSAI_LIST
---

## -description

The **WWAN_SNSSAI_LIST** structure represents a list of single Network Slice Selection Assistance Information (S-NSSAIs) that are allowed in the current PLMN or registration area.

## -struct-fields

### -field ElementCount

The number of elements in the S-NSSAI list.

### -field Snssais

An array of [**WWAN_SINGLE_NSSAI**](ns-wwan-wwan_single_nssai.md) structures that represent the allowed S-NSSAIs.

## -remarks

## -see-also

[**WWAN_SINGLE_NSSAI**](ns-wwan-wwan_single_nssai.md)