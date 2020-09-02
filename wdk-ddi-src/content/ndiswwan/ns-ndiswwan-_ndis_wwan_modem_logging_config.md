---
UID: NS:ndiswwan._NDIS_WWAN_MODEM_LOGGING_CONFIG
title: _NDIS_WWAN_MODEM_LOGGING_CONFIG (ndiswwan.h)
description: The NDIS_WWAN_MODEM_LOGGING_CONFIG structure describes the current modem logging configuration for a modem.
tech.root: netvista
ms.assetid: 04E5AFB1-0280-4862-B147-579B064AFF31
ms.date: 04/11/2019
keywords: ["NDIS_WWAN_MODEM_LOGGING_CONFIG structure"]
ms.keywords: _NDIS_WWAN_MODEM_LOGGING_CONFIG, NDIS_WWAN_MODEM_LOGGING_CONFIG, *PNDIS_WWAN_MODEM_LOGGING_CONFIG,
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
req.typenames: NDIS_WWAN_MODEM_LOGGING_CONFIG, *PNDIS_WWAN_MODEM_LOGGING_CONFIG
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_MODEM_LOGGING_CONFIG
 - ndiswwan/_NDIS_WWAN_MODEM_LOGGING_CONFIG
 - PNDIS_WWAN_MODEM_LOGGING_CONFIG
 - ndiswwan/PNDIS_WWAN_MODEM_LOGGING_CONFIG
 - NDIS_WWAN_MODEM_LOGGING_CONFIG
 - ndiswwan/NDIS_WWAN_MODEM_LOGGING_CONFIG
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_MODEM_LOGGING_CONFIG
---

# _NDIS_WWAN_MODEM_LOGGING_CONFIG structure


## -description

The **NDIS_WWAN_MODEM_LOGGING_CONFIG** structure describes the current modem logging configuration for a modem.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_MODEM_LOGGING_CONFIG** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_MODEM_LOGGING_CONFIG_REVISION_1 |
| Size | sizeof(NDIS_WWAN_MODEM_LOGGING_CONFIG) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |

### -field ModemLoggingConfig

A formatted [**WWAN_MODEM_LOGGING_CONFIG**](../wwan/ns-wwan-_wwan_modem_logging_config.md) structure that describes the modem logging configuration.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-modem-logging-config) status notification in response to a previous [OID_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-logging-config) Query or Set request.

## -see-also

[MB modem logging with DSS](https://docs.microsoft.com/windows-hardware/drivers/network/mb-modem-logging-with-dss)

[OID_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-logging-config)

[NDIS_STATUS_WWAN_MODEM_LOGGING_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-modem-logging-config)

[**WWAN_MODEM_LOGGING_CONFIG**](../wwan/ns-wwan-_wwan_modem_logging_config.md)

