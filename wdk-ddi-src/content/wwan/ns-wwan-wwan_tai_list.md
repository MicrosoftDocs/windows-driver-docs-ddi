---
UID: NS:wwan._WWAN_TAI_LIST
tech.root: netvista
title: WWAN_TAI_LIST
ms.date: 01/07/2022
targetos: Windows
description: The **WWAN_TAI_LIST** structure represents a Tracking Area Identity (TAI) list.
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
req.typenames: WWAN_TAI_LIST, *PWWAN_TAI_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_TAI_LIST
 - PWWAN_TAI_LIST
 - WWAN_TAI_LIST
f1_keywords:
 - _WWAN_TAI_LIST
 - wwan/_WWAN_TAI_LIST
 - PWWAN_TAI_LIST
 - wwan/PWWAN_TAI_LIST
 - WWAN_TAI_LIST
 - wwan/WWAN_TAI_LIST
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_TAI_LIST
---

## -description

The **WWAN_TAI_LIST** structure represents one or more Tracking Area Identity (TAI) lists. 

## -struct-fields

### -field TaiListType

A value from the [**WWAN_STRUCT_TYPE**](ne-wwan-_wwan_struct_type.md) enumeration that represents the type of the TAI list.

### -field DataBuffer

The TAI list data. The format is either [**WWAN_TAI_LIST_SINGLE_PLMN**](ns-wwan-wwan_tai_list_single_plmn.md) or [**WWAN_TAI_LIST_MULTI_PLMN**](ns-wwan-wwan_tai_list_multi_plmn.md).

## -remarks

## -see-also

[**WWAN_STRUCT_TYPE**](ne-wwan-_wwan_struct_type.md)

[**WWAN_TAI_LIST_SINGLE_PLMN**](ns-wwan-wwan_tai_list_single_plmn.md)

[**WWAN_TAI_LIST_MULTI_PLMN**](ns-wwan-wwan_tai_list_multi_plmn.md)