---
UID: NE:wwan._WWAN_MODEM_CONFIG_REASON
title: _WWAN_MODEM_CONFIG_REASON (wwan.h)
description: The WWAN_MODEM_CONFIG_REASON enumeration lists definitions for reasons why a modem's configuration state change was triggered.
old-location: netvista\wwan_modem_config_reason.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_MODEM_CONFIG_REASON enumeration"]
ms.keywords: "*PWWAN_MODEM_CONFIG_REASON, PWWAN_MODEM_CONFIG_REASON, PWWAN_MODEM_CONFIG_REASON enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_MODEM_CONFIG_REASON, WWAN_MODEM_CONFIG_REASON enumeration [Network Drivers Starting with Windows Vista], WwanModemConfigReasonActivationFailure, WwanModemConfigReasonConfigFileUpdate, WwanModemConfigReasonIMSIReset, WwanModemConfigReasonMax, WwanModemConfigReasonModemRecovery, WwanModemConfigReasonModemReset, WwanModemConfigReasonNOSIM, WwanModemConfigReasonNone, WwanModemConfigReasonSIMDetected, WwanModemConfigReasonSIMRemoved, _WWAN_MODEM_CONFIG_REASON, netvista.wwan_modem_config_reason, wwan/PWWAN_MODEM_CONFIG_REASON, wwan/WWAN_MODEM_CONFIG_REASON, wwan/WwanModemConfigReasonActivationFailure, wwan/WwanModemConfigReasonConfigFileUpdate, wwan/WwanModemConfigReasonIMSIReset, wwan/WwanModemConfigReasonMax, wwan/WwanModemConfigReasonModemRecovery, wwan/WwanModemConfigReasonModemReset, wwan/WwanModemConfigReasonNOSIM, wwan/WwanModemConfigReasonNone, wwan/WwanModemConfigReasonSIMDetected, wwan/WwanModemConfigReasonSIMRemoved"
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
req.typenames: WWAN_MODEM_CONFIG_REASON, *PWWAN_MODEM_CONFIG_REASON
f1_keywords:
 - _WWAN_MODEM_CONFIG_REASON
 - wwan/_WWAN_MODEM_CONFIG_REASON
 - PWWAN_MODEM_CONFIG_REASON
 - wwan/PWWAN_MODEM_CONFIG_REASON
 - WWAN_MODEM_CONFIG_REASON
 - wwan/WWAN_MODEM_CONFIG_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_MODEM_CONFIG_REASON
 - PWWAN_MODEM_CONFIG_REASON
 - WWAN_MODEM_CONFIG_REASON
---

# _WWAN_MODEM_CONFIG_REASON enumeration


## -description

The <b>WWAN_MODEM_CONFIG_REASON</b> enumeration lists definitions for reasons why a modem's configuration state change was triggered.

## -enum-fields

### -field WwanModemConfigReasonNone

Default value that can be used if other optional reasons are not supported.

### -field WwanModemConfigReasonSIMDetected

Required. A SIM card was detected by a modem.

### -field WwanModemConfigReasonNOSIM

Optional. There is no SIM card.

### -field WwanModemConfigReasonIMSIReset

Optional. A SIM card was reset with new IMSI programmed into it.

### -field WwanModemConfigReasonActivationFailure

Optional. Activation of a new configuration failed.

### -field WwanModemConfigReasonConfigFileUpdate

Optional. A new configuration file was updated by the host.

### -field WwanModemConfigReasonModemReset

Optional. The modem reset and configuration was not lost.

### -field WwanModemConfigReasonModemRecovery

Required. The modem reset and configuration was restored to default.

### -field WwanModemConfigReasonMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -see-also

[WWAN_MODEM_CONFIG_INFO](ns-wwan-_wwan_modem_config_info.md)

