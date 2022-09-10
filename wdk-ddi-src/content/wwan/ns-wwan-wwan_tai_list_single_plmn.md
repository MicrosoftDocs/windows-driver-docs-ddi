---
UID: NS:wwan._WWAN_TAI_LIST_SINGLE_PLMN
tech.root: netvista
title: WWAN_TAI_LIST_SINGLE_PLMN
ms.date: 01/07/2022
targetos: Windows
description: The WWAN_TAI_LIST structure represents a list of Tracking Area Codes (TACs) that belong to a single PLMN.
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
req.typenames: WWAN_TAI_LIST_SINGLE_PLMN, *PWWAN_TAI_LIST_SINGLE_PLMN
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_TAI_LIST_SINGLE_PLMN
 - PWWAN_TAI_LIST_SINGLE_PLMN
 - WWAN_TAI_LIST_SINGLE_PLMN
f1_keywords:
 - _WWAN_TAI_LIST_SINGLE_PLMN
 - wwan/_WWAN_TAI_LIST_SINGLE_PLMN
 - PWWAN_TAI_LIST_SINGLE_PLMN
 - wwan/PWWAN_TAI_LIST_SINGLE_PLMN
 - WWAN_TAI_LIST_SINGLE_PLMN
 - wwan/WWAN_TAI_LIST_SINGLE_PLMN
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_TAI_LIST_SINGLE_PLMN
---

## -description

The **WWAN_TAI_LIST** structure represents a list of Tracking Area Codes (TACs) that belong to a single PLMN (the Mobile Country Code (MCC) and Mobile Network Code (MNC)). The TAC values can be consecutive or nonconsecutive. 

## -struct-fields

### -field Plmn

A [**WWAN_PLMN**](ns-wwan-wwan_plmn.md) structure that represents the PLMN.

### -field ElementCount

The number of elements in the TAC list.

### -field Tacs

The TAC list. The ElementCount field specifies the number of elements.

## -remarks

## -see-also

[**WWAN_PLMN**](ns-wwan-wwan_plmn.md)

[**WWAN_TAI_LIST_MULTI_PLMN**](ns-wwan-wwan_tai_list_multi_plmn.md)