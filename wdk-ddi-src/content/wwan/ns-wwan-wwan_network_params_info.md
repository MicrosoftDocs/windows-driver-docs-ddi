---
UID: NS:wwan._WWAN_NETWORK_PARAMS_INFO
tech.root: 
title: WWAN_NETWORK_PARAMS_INFO
ms.date: 
targetos: Windows
description: 
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

WWAN_NETWORK_PARAMS_INFO is a data structure for NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE notifications.

## -struct-fields

### -field CurrentMicoIndication

Indicates the current use of Mobile Initiated Connection (MICO) mode. Valid only if NetworkConfigurationsNeeded is 1 in the query request.

### -field CurrentDRXParams

Valid only if NetworkConfigurationsNeeded is 1 in the query request.

## -remarks

## -see-also

[NDIS_STATUS_WWAN_NETWORK_PARAMS_STATE](/windows-hardware/drivers/network/ndis-status-wwan-sms-status)