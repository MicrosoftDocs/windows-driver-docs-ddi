---
UID: NS:wwan._WWAN_TAI_LIST_MULTI_PLMN
tech.root: netvista
title: WWAN_TAI_LIST_MULTI_PLMN
ms.date: 01/07/2022
targetos: Windows
description: The WWAN_TAI_LIST_MULTI_PLMN structure represents a list of Tracking Area Identities (TAIs) that belong to different PLMNs.
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
req.typenames: WWAN_TAI_LIST_MULTI_PLMN, *PWWAN_TAI_LIST_MULTI_PLMN
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_TAI_LIST_MULTI_PLMN
 - PWWAN_TAI_LIST_MULTI_PLMN
 - WWAN_TAI_LIST_MULTI_PLMN
f1_keywords:
 - _WWAN_TAI_LIST_MULTI_PLMN
 - wwan/_WWAN_TAI_LIST_MULTI_PLMN
 - PWWAN_TAI_LIST_MULTI_PLMN
 - wwan/PWWAN_TAI_LIST_MULTI_PLMN
 - WWAN_TAI_LIST_MULTI_PLMN
 - wwan/WWAN_TAI_LIST_MULTI_PLMN
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_TAI_LIST_MULTI_PLMN
---

## -description

The **WWAN_TAI_LIST_MULTI_PLMN** structure represents a list of Tracking Area Identities (TAIs) that belong to different PLMNs (the Mobile Country Code (MCC) and Mobile Network Code (MNC)).

## -struct-fields

### -field ElementCount

The number of elements in the TAI list.

### -field Tais

A list of [**WWAN_SINGLE_TAI**](ns-wwan-wwan_single_tai.md) structures. The ElementCount field specifies the number of elements.

## -remarks

## -see-also

[**WWAN_SINGLE_TAI**](ns-wwan-wwan_single_tai.md) 

[**WWAN_TAI_LIST_SINGLE_PLMN**](ns-wwan-wwan_tai_list_single_plmn.md)

