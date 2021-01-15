---
UID: NS:wwan._WWAN_MODEM_LOGGING_CONFIG
title: _WWAN_MODEM_LOGGING_CONFIG (wwan.h)
description: The WWAN_MODEM_LOGGING_CONFIG structure describes the current modem logging configuration for a modem.
tech.root: netvista
ms.date: 04/11/2019
keywords: ["WWAN_MODEM_LOGGING_CONFIG structure"]
ms.keywords: _WWAN_MODEM_LOGGING_CONFIG, WWAN_MODEM_LOGGING_CONFIG, *PWWAN_MODEM_LOGGING_CONFIG,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WWAN_MODEM_LOGGING_CONFIG, *PWWAN_MODEM_LOGGING_CONFIG
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WWAN_MODEM_LOGGING_CONFIG
 - wwan/_WWAN_MODEM_LOGGING_CONFIG
 - PWWAN_MODEM_LOGGING_CONFIG
 - wwan/PWWAN_MODEM_LOGGING_CONFIG
 - WWAN_MODEM_LOGGING_CONFIG
 - wwan/WWAN_MODEM_LOGGING_CONFIG
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_MODEM_LOGGING_CONFIG
 - PWWAN_MODEM_LOGGING_CONFIG
 - WWAN_MODEM_LOGGING_CONFIG
---

# _WWAN_MODEM_LOGGING_CONFIG structure


## -description

The **WWAN_MODEM_LOGGING_CONFIG** structure describes the current modem logging configuration for a modem.

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.

### -field MaxSegmentSize

The segment size, in kilobytes (KB), for each fragment sent by the modem. If the maximum fragment size supported by the modem for Device Service Commands exceeds the value set, then this value is set to the maximum supported segment size.

### -field MaxFlushTime

The time, in milliseconds, indicating the maximum time the modem waits before sending a log fragment. If the logs collected don't reach **MaxSegmentSize** within the **MaxFlushTime** duration since the last log fragment was sent, then a log fragment is sent regardless of its size. If there is no logging data, then no notification is sent. If the device cannot handle smaller flush times, then the device returns the time that it can handle in the response. The response to an [OID_WWAN_MODEM_LOGGING_CONFIG](/windows-hardware/drivers/network/oid-wwan-modem-logging-config) Query or Set request contains the currently configured **MaxFlushTime**.

### -field LevelConfig

A [**WWAN_MODEM_LOGGING_LEVEL_CONFIG**](../wwan/ne-wwan-_wwan_modem_logging_level_config.md) value that configures the level for which logs are collected. The response to an [OID_WWAN_MODEM_LOGGING_CONFIG](/windows-hardware/drivers/network/oid-wwan-modem-logging-config) Query or Set request contains the currently configured **LevelConfig**.

## -remarks

This structure is used in the [**NDIS_WWAN_MODEM_LOGGING_CONFIG**](../ndiswwan/ns-ndiswwan-_ndis_wwan_modem_logging_config.md) structure.

## -see-also

[MB modem logging with DSS](/windows-hardware/drivers/network/mb-modem-logging-with-dss)

[OID_WWAN_MODEM_LOGGING_CONFIG](/windows-hardware/drivers/network/oid-wwan-modem-logging-config)

[**NDIS_WWAN_MODEM_LOGGING_CONFIG**](../ndiswwan/ns-ndiswwan-_ndis_wwan_modem_logging_config.md)

