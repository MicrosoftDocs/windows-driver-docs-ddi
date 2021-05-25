---
UID: NS:wwan._WWAN_SET_REGISTER_PARAMS
tech.root: 
title: WWAN_SET_REGISTER_PARAMS
description: The WWAN_SET_REGISTER_PARAMS structure is used for OID_WWAN_REGISTER_PARAMS set requests.
ms.date: 
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
req.typenames: WWAN_SET_REGISTER_PARAMS, *PWWAN_SET_REGISTER_PARAMS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SET_REGISTER_PARAMS
 - PWWAN_SET_REGISTER_PARAMS
 - WWAN_SET_REGISTER_PARAMS
f1_keywords:
 - _WWAN_SET_REGISTER_PARAMS
 - wwan/_WWAN_SET_REGISTER_PARAMS
 - PWWAN_SET_REGISTER_PARAMS
 - wwan/PWWAN_SET_REGISTER_PARAMS
 - WWAN_SET_REGISTER_PARAMS
 - wwan/WWAN_SET_REGISTER_PARAMS
dev_langs:
 - c++
---

## -description

The **WWAN_SET_REGISTER_PARAMS** structure is used for [OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params) set requests.

## -struct-fields

### -field MicoMode

A value from the [**WWAN_MICO_MODE**](ne-wwan-wwan_mico_mode.md) enumeration that represents the Mobile Initiated Connection (MICO) mode requested by the host.

### -field DRXParam

A value from the [**WWAN_DRX_PARAMS**](ne-wwan-wwan_drx_params.md) enumeration that represents the configuration of Discontinuous Reception (DRX) settings requested by the host.

### -field LADNInfo

A value from the [**WWAN_LADN_IND_REQUEST**](ne-wwan-wwan_ladn_ind_request.md) enumeration that represents the Local Area Data Networks (LADN) information requested by the host.

### -field DefaultPDUSessionHint

A value from the [**WWAN_DEFAULT_PDU_SESSION_HINT**](ne-wwan-wwan_default_pdu_session_hint.md) enumeration that represents a hint that the host will possibly establish the default protocol data unit (PDU) session immediately after the registration is complete. Since this depends on several policies, it may not happen.

### -field ReRegisterIfNeeded

This is a forced re-registration indicator.

When this structure is used with [OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params) set requests:

* If the value is **1** and the device is currently registered or in the middle of registration, the modem shall evaluate whether any of the registration parameters contained in this set request are different than those used in the previous registration request toward the network. If the parameters are different, the modem shall de-register from the network and re-register using the current registration parameters. All normal procedures related to de-registration and registration, including sending appropriate events at appropriate times, shall be performed.

* A value of **0** indicates that forced re-registration is not requested.

* This is a one-time indicator. The modem shall use this only once upon receiving this set request.

All other values are reserved.

### -field PreConfiguredNSSAIListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) object that represents a pre-configured Single Network Slice Selection Assistance Information (S-NSSAI). The host will send exactly one S-NSSAI if the modem has zero pre-configured default S-NSSAIs.

## -see-also

[OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params)

[NDIS_STATUS_WWAN_REGISTER_PARAMS_STATE](/windows-hardware/drivers/network/ndis-status-wwan-register-params-state)

[**WWAN_MICO_MODE**](ne-wwan-wwan_mico_mode.md)

[**WWAN_DRX_PARAMS**](ne-wwan-wwan_drx_params.md)

[**WWAN_LADN_IND_REQUEST**](ne-wwan-wwan_ladn_ind_request.md)

[**WWAN_DEFAULT_PDU_SESSION_HINT**](ne-wwan-wwan_default_pdu_session_hint.md)

[**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md)
