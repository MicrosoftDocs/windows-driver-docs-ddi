---
UID: NS:wwan._WWAN_LADN_LIST
tech.root: netvista
title: WWAN_LADN_LIST
ms.date: 01/14/2022
targetos: Windows
description: The WWAN_LADN_LIST structure represents a list of Local Area Data Networks (LADNs).
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
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_LADN_LIST, *PWWAN_LADN_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_LADN_LIST
 - PWWAN_LADN_LIST
 - WWAN_LADN_LIST
f1_keywords:
 - _WWAN_LADN_LIST
 - wwan/_WWAN_LADN_LIST
 - PWWAN_LADN_LIST
 - wwan/PWWAN_LADN_LIST
 - WWAN_LADN_LIST
 - wwan/WWAN_LADN_LIST
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_LADN_LIST
---

## -description

The **WWAN_LADN_LIST** structure represents a list of Local Area Data Networks (LADNs).

## -struct-fields

### -field ElementCount

The number of elements in the LADN list.

### -field Ladns

An array of [**WWAN_LADN**](ns-wwan-wwan_ladn.md) structures that represent the LADN list.

## -remarks

## -see-also

[**WWAN_LADN**](ns-wwan-wwan_ladn.md)