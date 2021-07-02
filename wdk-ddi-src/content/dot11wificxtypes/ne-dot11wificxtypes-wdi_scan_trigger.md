---
UID: NE:dot11wificxtypes._WDI_SCAN_TRIGGER (dot11wificxtypes.h)
tech.root: netvista
title: WDI_SCAN_TRIGGER
ms.date: 06/23/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_SCAN_TRIGGER enum defines scan trigger values.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_SCAN_TRIGGER
 - WDI_SCAN_TRIGGER
f1_keywords:
 - _WDI_SCAN_TRIGGER
 - dot11wificxtypes/_WDI_SCAN_TRIGGER
 - WDI_SCAN_TRIGGER
 - dot11wificxtypes/WDI_SCAN_TRIGGER
dev_langs:
 - c++
---

## -description

The **WDI_SCAN_TRIGGER** enumeration defines scan trigger values.

## -enum-fields

### -field WDI_SCAN_TRIGGER_MANUAL

The scan was initiated due to a user or application trigger. If this is set, the port must perform a complete scan on all supported channels.

### -field WDI_SCAN_TRIGGER_BACKGROUND

The scan was initiated due to some background activity. If this is set, the port can perform a complete scan, a partial scan on a subset of supported channels, or no scan.

### -field WDI_SCAN_TRIGGER_ROAM

The scan was initiated for roaming purposes. If the adapter was doing background scans internally and has recent results, it can perform only a subset or no scan. If it does not have recent results, it should perform an appropriate scan.

### -field WDI_SCAN_TRIGGER_CONNECT

The scan was initiated for connecting. This connect may be a first time connect or a connect after a disconnection. The port must always honor this request to perform a scan.

### -field WDI_SCAN_TRIGGER_ANQP_QUERY

The scan was initiated for performing an ANQP query.

### -field WDI_SCAN_TRIGGER_FAST_ROAM

The scan was initiated for roaming purposes, and the host has additional information (for example, neighbor reports or instant connect last channel) to put in specific values in the scan request (such as SSID, BSSID, or band channel).

### -field WDI_SCAN_TRIGGER_FTM

The scan was initiated to search for FTM enabled STAs and the host has additional information (such as channel, BSSID, etc). The port must always honor this request to perform a scan.

## -remarks

The **WDI_SCAN_TRIGGER** enum is used in the payload buffer of the [**WDI_TLV_SCAN_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-scan-mode) TLV.

## -see-also

[**WDI_TLV_SCAN_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-scan-mode)