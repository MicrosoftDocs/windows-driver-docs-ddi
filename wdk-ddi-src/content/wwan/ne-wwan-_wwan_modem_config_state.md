---
UID: NE:wwan._WWAN_MODEM_CONFIG_STATE
title: _WWAN_MODEM_CONFIG_STATE (wwan.h)
description: The WWAN_MODEM_CONFIG_STATE enumeration lists definitions used by the modem to inform the OS about its modem configuration state.
old-location: netvista\wwan_modem_config_state.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_MODEM_CONFIG_STATE enumeration"]
ms.keywords: "*PWWAN_MODEM_CONFIG_STATE, PWWAN_MODEM_CONFIG_STATE, PWWAN_MODEM_CONFIG_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_MODEM_CONFIG_STATE, WWAN_MODEM_CONFIG_STATE enumeration [Network Drivers Starting with Windows Vista], WwanModemConfigStateActivated, WwanModemConfigStateMax, WwanModemConfigStatePending, WwanModemConfigStateUnknown, _WWAN_MODEM_CONFIG_STATE, netvista.wwan_modem_config_state, wwan/PWWAN_MODEM_CONFIG_STATE, wwan/WWAN_MODEM_CONFIG_STATE, wwan/WwanModemConfigStateActivated, wwan/WwanModemConfigStateMax, wwan/WwanModemConfigStatePending, wwan/WwanModemConfigStateUnknown"
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
req.typenames: WWAN_MODEM_CONFIG_STATE, *PWWAN_MODEM_CONFIG_STATE
f1_keywords:
 - _WWAN_MODEM_CONFIG_STATE
 - wwan/_WWAN_MODEM_CONFIG_STATE
 - PWWAN_MODEM_CONFIG_STATE
 - wwan/PWWAN_MODEM_CONFIG_STATE
 - WWAN_MODEM_CONFIG_STATE
 - wwan/WWAN_MODEM_CONFIG_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_MODEM_CONFIG_STATE
 - PWWAN_MODEM_CONFIG_STATE
 - WWAN_MODEM_CONFIG_STATE
---

# _WWAN_MODEM_CONFIG_STATE enumeration


## -description

The <b>WWAN_MODEM_CONFIG_STATE</b> enumeration lists definitions used by the modem to inform the OS about its modem configuration state.

## -enum-fields

### -field WwanModemConfigStateUnknown

The modem configuration state is currently not available.

### -field WwanModemConfigStatePending

The modem is currently selecting the best suitable configuration file that matches the UICC info.

### -field WwanModemConfigStateActivated

The modem has completed its configuration and modem subcomponents are aware of the new configuration.

### -field WwanModemConfigStateMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -see-also

<a href="/previous-versions/mt813894(v=vs.85)">WWAN_MODEM_CONFIG_STATUS</a>

