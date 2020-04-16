---
UID: NS:ndiswwan._NDIS_WWAN_SET_MODEM_LOGGING_CONFIG
title: _NDIS_WWAN_SET_MODEM_LOGGING_CONFIG (ndiswwan.h)
description: The NDIS_WWAN_SET_MODEM_LOGGING_CONFIG structure specifies modem logging configuration for a modem.
tech.root: netvista
ms.assetid: 60555A58-2C1A-41FB-AE2C-E279C9BEC3CC
ms.date: 04/11/2019
keywords: ["_NDIS_WWAN_SET_MODEM_LOGGING_CONFIG structure"]
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_SET_MODEM_LOGGING_CONFIG"
ms.keywords: _NDIS_WWAN_SET_MODEM_LOGGING_CONFIG, NDIS_WWAN_SET_MODEM_LOGGING_CONFIG, *PNDIS_WWAN_SET_MODEM_LOGGING_CONFIG, 
req.header: ndiswwan.h
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
req.typenames: NDIS_WWAN_SET_MODEM_LOGGING_CONFIG, *PNDIS_WWAN_SET_MODEM_LOGGING_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_SET_MODEM_LOGGING_CONFIG
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _NDIS_WWAN_SET_MODEM_LOGGING_CONFIG structure

## -description

The **NDIS_WWAN_SET_MODEM_LOGGING_CONFIG** structure specifies modem logging configuration for a modem. 

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_MODEM_LOGGING_CONFIG** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_MODEM_LOGGING_CONFIG_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_MODEM_LOGGING_CONFIG) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field ModemLoggingConfig

A formatted [**WWAN_MODEM_LOGGING_CONFIG**](../wwan/ns-wwan-_wwan_modem_logging_config.md) structure that describes the modem logging configuration to set.

## -remarks

This structure is used in the payload of an [OID_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-logging-config) Set request.

## -see-also

[MB modem logging with DSS](https://docs.microsoft.com/windows-hardware/drivers/network/mb-modem-logging-with-dss)

[OID_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-logging-config)

[NDIS_STATUS_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-modem-logging-config)

[**WWAN_MODEM_LOGGING_CONFIG**](../wwan/ns-wwan-_wwan_modem_logging_config.md)
