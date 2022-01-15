---
UID: NS:wwan._WWAN_REJECTED_SNSSAI_LIST
tech.root: netvista
title: WWAN_REJECTED_SNSSAI_LIST
ms.date: 01/14/2022
targetos: Windows
description: The WWAN_REJECTED_SNSSAI_LIST structure represents a list of single Network Slice Selection Assistance Information (S-NSSAIs) that are not allowed in the current PLMN or registration area.
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
req.typenames: WWAN_REJECTED_SNSSAI_LIST, *PWWAN_REJECTED_SNSSAI_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_REJECTED_SNSSAI_LIST
 - PWWAN_REJECTED_SNSSAI_LIST
 - WWAN_REJECTED_SNSSAI_LIST
f1_keywords:
 - _WWAN_REJECTED_SNSSAI_LIST
 - wwan/_WWAN_REJECTED_SNSSAI_LIST
 - PWWAN_REJECTED_SNSSAI_LIST
 - wwan/PWWAN_REJECTED_SNSSAI_LIST
 - WWAN_REJECTED_SNSSAI_LIST
 - wwan/WWAN_REJECTED_SNSSAI_LIST
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_REJECTED_SNSSAI_LIST
---

## -description

The **WWAN_REJECTED_SNSSAI_LIST** structure represents a list of single Network Slice Selection Assistance Information (S-NSSAIs) that are not allowed in the current PLMN or registration area.

## -struct-fields

### -field ElementCount

The number of elements in the rejected S-NSSAIs list.

### -field Snssais

An array of [**WWAN_SINGLE_NSSAI**](ns-wwan-wwan_single_nssai.md) structures that represent the rejected S-NSSAIs.

## -remarks

## -see-also

[**WWAN_SINGLE_NSSAI**](ns-wwan-wwan_single_nssai.md)

