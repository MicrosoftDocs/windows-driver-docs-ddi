---
UID: NS:wwan._WWAN_REGISTER_PARAMS_INFO
tech.root: 
title: WWAN_REGISTER_PARAMS_INFO
description: The WWAN_REGISTER_PARAMS_INFO structure represents data for NDIS_STATUS_WWAN_REGISTER_PARAMS_STATE notifications.
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
req.typenames: WWAN_REGISTER_PARAMS_INFO, *PWWAN_REGISTER_PARAMS_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_REGISTER_PARAMS_INFO
 - PWWAN_REGISTER_PARAMS_INFO
 - WWAN_REGISTER_PARAMS_INFO
f1_keywords:
 - _WWAN_REGISTER_PARAMS_INFO
 - wwan/_WWAN_REGISTER_PARAMS_INFO
 - PWWAN_REGISTER_PARAMS_INFO
 - wwan/PWWAN_REGISTER_PARAMS_INFO
 - WWAN_REGISTER_PARAMS_INFO
 - wwan/A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) object that represents a pre-configured Single Network Slice Selection Assistance Information (S-NSSAI). The host will send exactly one S-NSSAI if the modem has zero pre-configured default S-NSSAIs.


dev_langs:
 - c++
---

## -description

The **WWAN_REGISTER_PARAMS_INFO** structure represents data for NDIS_STATUS_WWAN_REGISTER_PARAMS_STATE notifications.

## -struct-fields

### -field MicoMode

A value from the [**WWAN_MICO_MODE**](ne-wwan-wwan_mico_mode.md) enumeration that represents the Mobile Initiated Connection (MICO) mode requested by the host.

### -field DRXParam

A value from the [**WWAN_DRX_PARAMS**](ne-wwan-wwan_drx_params.md) enumeration that represents the configuration of Discontinuous Reception (DRX) settings requested by the host.

### -field LADNInfo

A value from the [**WWAN_LADN_IND_REQUEST**](ne-wwan-wwan_ladn_ind_request.md) enumeration that represents the Local Area Data Networks (LADN) information requested by the host.

### -field PreConfiguredNSSAIListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) object that represents a pre-configured Single Network Slice Selection Assistance Information (S-NSSAI). The host will send exactly one S-NSSAI if the modem has zero pre-configured default S-NSSAIs.

## -remarks

## -see-also

