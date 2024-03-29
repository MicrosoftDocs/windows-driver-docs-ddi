---
UID: NS:wwan._WWAN_MODEM_CONFIG_INFO
title: _WWAN_MODEM_CONFIG_INFO (wwan.h)
description: The WWAN_MODEM_CONFIG_INFO structure represents the modem's configuration information.
old-location: netvista\wwan_modem_config_info.htm
tech.root: netvista
ms.date: 12/30/2021
keywords: ["WWAN_MODEM_CONFIG_INFO structure"]
ms.keywords: "*PWWAN_MODEM_CONFIG_INFO, PWWAN_MODEM_CONFIG_INFO, PWWAN_MODEM_CONFIG_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_MODEM_CONFIG_INFO, WWAN_MODEM_CONFIG_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_MODEM_CONFIG_INFO, netvista.wwan_modem_config_info, wwan/PWWAN_MODEM_CONFIG_INFO, wwan/WWAN_MODEM_CONFIG_INFO"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WWAN_MODEM_CONFIG_INFO, *PWWAN_MODEM_CONFIG_INFO
f1_keywords:
 - _WWAN_MODEM_CONFIG_INFO
 - wwan/_WWAN_MODEM_CONFIG_INFO
 - PWWAN_MODEM_CONFIG_INFO
 - wwan/PWWAN_MODEM_CONFIG_INFO
 - WWAN_MODEM_CONFIG_INFO
 - wwan/WWAN_MODEM_CONFIG_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_MODEM_CONFIG_INFO
 - PWWAN_MODEM_CONFIG_INFO
 - WWAN_MODEM_CONFIG_INFO
---

# _WWAN_MODEM_CONFIG_INFO structure


## -description

The <b>WWAN_MODEM_CONFIG_INFO</b> structure represents the modem's configuration information.

## -struct-fields

### -field ConfigMode

The modem's configuration mode. For a list of defined values, see <a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_modem_config_mode">WWAN_MODEM_CONFIG_MODE</a>.

### -field ConfigState

The modem's configuration state. For a list of defined values, see [**WWAN_MODEM_CONFIG_STATE**](ne-wwan-_wwan_modem_config_state.md).

### -field ConfigReason

The reason for the modem's configuration state change. For a list of defined values, see [**WWAN_MODEM_CONFIG_REASON**](ne-wwan-_wwan_modem_config_reason.md).

### -field PreviousConfigID

A formatted [**WWAN_MODEM_CONFIG_ID**](ns-wwan-_wwan_modem_config_id.md) structure that represents the modem's previous configuration ID.

### -field CurrentConfigID

A formatted [**WWAN_MODEM_CONFIG_ID**](ns-wwan-_wwan_modem_config_id.md) structure that represents the modem's current configuration ID.

### -field IsCurrentConfigDefault

A DWORD value that indicates if the current configuration is the default configuration.

### -field ConfigName

### -field NSSAIListHeader

A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) object that represents a pre-configured Single Network Slice Selection Assistance Information (S-NSSAI).

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-wwan-modem-config-info">NDIS_STATUS_WWAN_MODEM_CONFIG_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_modem_config_info">NDIS_WWAN_MODEM_CONFIG_INFO</a>



<a href="/windows-hardware/drivers/network/oid-wwan-modem-config-info">OID_WWAN_MODEM_CONFIG_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_modem_config_mode">WWAN_MODEM_CONFIG_MODE</a>



<a href="/previous-versions/mt813894(v=vs.85)">WWAN_MODEM_CONFIG_STATUS</a>

