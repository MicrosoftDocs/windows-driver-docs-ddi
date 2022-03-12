---
UID: NS:wwan._WWAN_NETWORK_PARAMS_INFO
tech.root: netvista
title: WWAN_NETWORK_PARAMS_INFO
description: The WWAN_NETWORK_PARAMS_INFO structure represents data for NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE notifications.
ms.date: 06/01/2021
targetos: Windows
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_NETWORK_PARAMS_INFO, *PWWAN_NETWORK_PARAMS_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NETWORK_PARAMS_INFO
 - PWWAN_NETWORK_PARAMS_INFO
 - WWAN_NETWORK_PARAMS_INFO
f1_keywords:
 - _WWAN_NETWORK_PARAMS_INFO
 - wwan/_WWAN_NETWORK_PARAMS_INFO
 - PWWAN_NETWORK_PARAMS_INFO
 - wwan/PWWAN_NETWORK_PARAMS_INFO
 - WWAN_NETWORK_PARAMS_INFO
 - wwan/WWAN_NETWORK_PARAMS_INFO
dev_langs:
 - c++
---

## -description

The **WWAN_NETWORK_PARAMS_INFO** structure represents network configuration data and policy information. Miniport drivers use this structure with [NDIS_WWAN_NETWORK_PARAMS_INFO](../ndiswwan/ns-ndiswwan-ndis_wwan_network_params_info.md) and [NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE](/windows-hardware/drivers/network/ndis-status-wwan-network-params-state) notifications to notify the host of network parameter updates.

## -struct-fields

### -field CurrentMicoIndication

Indicates the current use of Mobile Initiated Connection (MICO) mode. Valid only if NetworkConfigurationsNeeded is 1 in the query request.

### -field CurrentDRXParams

Valid only if NetworkConfigurationsNeeded is 1 in the query request.

### -field TaiList

The first 4 bytes are the offset to the **DataBuffer** containing a [**WWAN_TAI_LIST**](ns-wwan-wwan_tai_list.md), in bytes, calculated from the beginning of **WWAN_NETWORK_PARAMS_INFO**. The second 4 bytes are the size of **WWAN_TAI_LIST**, in bytes.

### -field AllowedNssaiList

The first 4 bytes are the offset to the **DataBuffer** containing a [**WWAN_SNSSAI_LIST**](ns-wwan-wwan_snssai_list.md), in bytes, calculated from the beginning of **WWAN_NETWORK_PARAMS_INFO**. The second 4 bytes are the size of **WWAN_SNSSAI_LIST**, in bytes.

### -field ConfiguredNssaiList

The first 4 bytes are the offset to the **DataBuffer** containing a [**WWAN_SNSSAI_LIST**](ns-wwan-wwan_snssai_list.md), in bytes, calculated from the beginning of **WWAN_NETWORK_PARAMS_INFO**. The second 4 bytes are the size of **WWAN_SNSSAI_LIST**, in bytes.

### -field RejectedNssaiList

The first 4 bytes are the offset to the **DataBuffer** containing a [**WWAN_REJECTED_SNSSAI_LIST**](ns-wwan-wwan_rejected_snssai_list.md), in bytes, calculated from the beginning of **WWAN_NETWORK_PARAMS_INFO**. The second 4 bytes are the size of **WWAN_REJECTED_SNSSAI_LIST**, in bytes.

### -field DefaultConfiguredNssaiList

The first 4 bytes are the offset to the **DataBuffer** containing a [**WWAN_SNSSAI_LIST**](ns-wwan-wwan_snssai_list.md), in bytes, calculated from the beginning of **WWAN_NETWORK_PARAMS_INFO**. The second 4 bytes are the size of **WWAN_SNSSAI_LIST**, in bytes.

### -field LadnList

The first 4 bytes are the offset to the **DataBuffer** containing a [**WWAN_LADN_LIST**](ns-wwan-wwan_ladn_list.md), in bytes, calculated from the beginning of **WWAN_NETWORK_PARAMS_INFO**. The second 4 bytes are the size of **WWAN_LADN_LIST**, in bytes.

### -field DataBuffer

A buffer containing **TaiList**, **AllowedNssaiList**, **ConfiguredNssaiList**, **RejectedNssaiList**, **DefaultConfiguredNssaiList**, and **LadnList** immediately follow the last named field of **WWAN_NETWORK_PARAMS_INFO** (**LadnList**), in that order, without any unused space in between.

## -remarks

## -see-also

[NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE](/windows-hardware/drivers/network/ndis-status-wwan-network-params-state)

[NDIS_WWAN_NETWORK_PARAMS_INFO](../ndiswwan/ns-ndiswwan-ndis_wwan_network_params_info.md)
