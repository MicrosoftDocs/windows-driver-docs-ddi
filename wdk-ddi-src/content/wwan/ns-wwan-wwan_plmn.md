---
UID: NS:wwan._WWAN_PLMN
tech.root: netvista
title: WWAN_PLMN
ms.date: 01/11/2022
targetos: Windows
description: The WWAN_PLMN structure represents a Mobile Country Code (MCC) and Mobile Network Code (MNC).
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
req.typenames: WWAN_PLMN, *PWWAN_PLMN
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PLMN
 - PWWAN_PLMN
 - WWAN_PLMN
f1_keywords:
 - _WWAN_PLMN
 - wwan/_WWAN_PLMN
 - PWWAN_PLMN
 - wwan/PWWAN_PLMN
 - WWAN_PLMN
 - wwan/WWAN_PLMN
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_PLMN
---

## -description

The **WWAN_PLMN** structure represents a Mobile Country Code (MCC) and Mobile Network Code (MNC).

## -struct-fields

### -field Mcc

Mobile Country Code of 3 decimal digits. The least significant 12 bits contains BCD-encoded 3 decimal digits sequentially for the MCC, with the last digit of the MCC in the least significant 4 bits. The unused bits in the UINT16 integer must be zeros.

### -field Mnc

Mobile Network Code of either 3 or 2 decimal digits. The most significant bit indicates whether the MNC has 2 decimal digits or 3 decimal digits. If this bit has 1, the MNC has 2 decimal digits and the least significant 8 bits contains them in BCD-encoded form sequentially, with the last digit of the MNC in the least significant 4 bits. If the most significant bit has 0, the MNC has 3 decimal digits and the least significant 12 bits contains them in BCD-encoded form sequentially, with the last digit of the MNC in the least significant 4 bits. The unused bits in the UINT16 integer must be zeros.

## -remarks

## -see-also

[**WWAN_TAI_LIST_SINGLE_PLMN**](ns-wwan-wwan_tai_list_single_plmn.md)

