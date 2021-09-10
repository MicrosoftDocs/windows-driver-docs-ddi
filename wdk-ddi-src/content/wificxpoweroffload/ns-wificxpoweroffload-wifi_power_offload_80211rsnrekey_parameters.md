---
UID: NS:wificxpoweroffload._WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
tech.root: netvista
title: WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS (wificxpoweroffload.h)
ms.date: 09/10/2021
targetos: Windows
description: The WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS structure contains parameters for an 802.11 RSN rekey low power protocol offload to a Wi-Fi adapter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffload.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxpoweroffload.h
api_name:
 - _WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
 - WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
f1_keywords:
 - _WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
 - wificxpoweroffload/_WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
 - WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
 - wificxpoweroffload/WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS
dev_langs:
 - c++
---

## -description

The **WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS** structure contains parameters for an 802.11 RSN rekey low power protocol offload to a Wi-Fi adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field ProtocolOffloadId

The identifier for this protocol offload.

### -field ReplayCounter

A UINT64 value that specifies the replay counter.

### -field KCKLength

The length of the IEEE 802.11 key confirmation key (KCK).

### -field KEKLength

The length of the IEEE 802.11 key encryption key (KEK).

### -field KCK

A UCHAR array that specifies the KCK.

### -field KEK

A UCHAR array that specifies the KEK.

## -remarks

Call [**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters_init.md) to initialize this structure and fill in its **Size** field. Then call [**WifiPowerOffloadGet80211RSNRekeyParameters**](nf-wificxpoweroffload-wifipoweroffloadget80211rsnrekeyparameters.md) to fill in the remaining members of the structure.

## -see-also

[**WIFI_POWER_OFFLOAD_80211RSNREKEY_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_80211rsnrekey_parameters_init.md)

[**WifiPowerOffloadGet80211RSNRekeyParameters**](nf-wificxpoweroffload-wifipoweroffloadget80211rsnrekeyparameters.md)