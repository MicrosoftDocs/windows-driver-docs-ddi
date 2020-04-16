---
UID: NE:wwan._WWAN_MODEM_LOGGING_LEVEL_CONFIG
title: _WWAN_MODEM_LOGGING_LEVEL_CONFIG (wwan.h)
description: The WWAN_MODEM_LOGGING_LEVEL_CONFIG enumeration specifies the level for which modem logs are collected.
tech.root: netvista
ms.assetid: BA48D00B-4D26-4298-BA39-E87D27F4F299
ms.date: 04/11/2019
keywords: ["_WWAN_MODEM_LOGGING_LEVEL_CONFIG enumeration"]
f1_keywords:
 - "wwan/_WWAN_MODEM_LOGGING_LEVEL_CONFIG"
ms.keywords: _WWAN_MODEM_LOGGING_LEVEL_CONFIG WWAN_MODEM_LOGGING_LEVEL_CONFIG *PWWAN_MODEM_LOGGING_LEVEL_CONFIG 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10 version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_MODEM_LOGGING_LEVEL_CONFIG *PWWAN_MODEM_LOGGING_LEVEL_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_MODEM_LOGGING_LEVEL_CONFIG
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_MODEM_LOGGING_LEVEL_CONFIG enumeration

## -description

The **WWAN_MODEM_LOGGING_LEVEL_CONFIG** enumeration specifies the level for which modem logs are collected.

## -enum-fields

### -field WwanModemLoggingLevelProd

Intended for telemetry collection from a retail or production population. The resulting log should be capsule-sized and contains key modem or MBB state or failure information only.

### -field WwanModemLoggingLevelLabVerbose

Intended for the development of MBB products with low maturity. Verbose full-stack capture of modems. The resulting modem capture should enable the IHV to replay and fully recover the capture during the log.

### -field WwanModemLoggingLevelLabMedium

Intended for verification and field testing of MBB products with relative maturity and stability. The level of detail and verbosity provides enough data points for IHV engineers to triage most MBB failures.

### -field WwanModemLoggingLevelLabLow

Intended for self-host-level logging. Summary-level capture of full-stack capture modems. Enables a highlight-level understanding of the modem's state and OS interactions.

### -field WwanModemLoggingLevelOem

Reserved for OEM and IHV internal usage.

### -field WwanModemLoggingLevelMax

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_MODEM_LOGGING_CONFIG**](../wwan/ns-wwan-_wwan_modem_logging_config.md) structure.

## -see-also

[MB modem logging with DSS](https://docs.microsoft.com/windows-hardware/drivers/network/mb-modem-logging-with-dss)

[OID_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-logging-config)

[**WWAN_MODEM_LOGGING_CONFIG**](../wwan/ns-wwan-_wwan_modem_logging_config.md)
