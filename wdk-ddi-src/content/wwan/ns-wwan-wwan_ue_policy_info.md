---
UID: NS:wwan._WWAN_UE_POLICY_INFO
tech.root: netvista
title: WWAN_UE_POLICY_INFO
ms.date: 03/11/2022
targetos: Windows
description: The WWAN_UE_POLICY_INFO structure represents the UE policy information of the MB device.
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
req.typenames: WWAN_UE_POLICY_INFO, *PWWAN_UE_POLICY_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_UE_POLICY_INFO
 - PWWAN_UE_POLICY_INFO
 - WWAN_UE_POLICY_INFO
f1_keywords:
 - _WWAN_UE_POLICY_INFO
 - wwan/_WWAN_UE_POLICY_INFO
 - PWWAN_UE_POLICY_INFO
 - wwan/PWWAN_UE_POLICY_INFO
 - WWAN_UE_POLICY_INFO
 - wwan/WWAN_UE_POLICY_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_UE_POLICY_INFO
---

## -description

The **WWAN_UE_POLICY_INFO** structure represents the UE policy information of the MB device.

## -struct-fields

### -field RawTdOnlyData

A [**WWAN_OFFSET_SIZE_ELEMENT**](ns-wwan-wwan_offset_size_element.md) structure. The first 4 bytes are the offset to the data buffer that contains the raw data of MBIM_TLV_TYPE_URSP_RULES_TD_ONLY, in bytes, calculated from the beginning of **WWAN_UE_POLICY_INFO**.
The second 4 bytes are the size of the raw data of MBIM_TLV_TYPE_URSP_RULES_TD_ONLY, in bytes.

## -remarks

**WWAN_UE_POLICY_INFO** is used by the  [**NDIS_WWAN_UE_POLICY_INFO**]../ndiswwan/ns-ndiswwan-ndis_wwan_ue_policy_info.md) structure.

## -see-also

[**NDIS_WWAN_UE_POLICY_INFO**](../ndiswwan/ns-ndiswwan-ndis_wwan_ue_policy_info.md)

[OID_WWAN_UE_POLICY](/windows-hardware/drivers/network/oid-wwan-ue-policy)