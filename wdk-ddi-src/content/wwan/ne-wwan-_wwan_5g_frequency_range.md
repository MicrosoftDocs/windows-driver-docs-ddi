---
UID: NE:wwan._WWAN_5G_FREQUENCY_RANGE
title: _WWAN_5G_FREQUENCY_RANGE (wwan.h)
description: The WWAN_5G_FREQUENCY_RANGE enumeration specifies the frequency ranges that the device is using for 5G.
tech.root: netvista
ms.assetid: 63C14301-2D71-4F19-937E-4FBC1A43DFBC
ms.date: 04/05/2019
keywords: ["WWAN_5G_FREQUENCY_RANGE enumeration"]
f1_keywords:
 - "wwan/_WWAN_5G_FREQUENCY_RANGE"
 - "_WWAN_5G_FREQUENCY_RANGE"
ms.keywords: _WWAN_5G_FREQUENCY_RANGE, WWAN_5G_FREQUENCY_RANGE, *PWWAN_5G_FREQUENCY_RANGE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_5G_FREQUENCY_RANGE, *PWWAN_5G_FREQUENCY_RANGE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_5G_FREQUENCY_RANGE
targetos: Windows
ms.custom: 19H1
---

# _WWAN_5G_FREQUENCY_RANGE enumeration

## -description

The **WWAN_5G_FREQUENCY_RANGE** enumeration specifies the frequency ranges that the device is using for 5G.

## -enum-fields

### -field Wwan5GFrequencyRangeUnknown  

Indicates that the system type is not 5G.

### -field Wwan5GFrequencyRange1   

Indicates Frequency range 1 (FR1) in <a href="https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=3283">3GPP TS 38.101-1</a> (Sub-6G).

### -field Wwan5GFrequencyRange2  

Indicates FR2 in <a href="https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=3284">3GPP TS 38.101-2</a> (mmWave).

### -field Wwan5GFrequencyRange1AndRange2  

Indicates that both FR1 and FR2 carriers are connected.

## -remarks

This enumeration is used in the [**WWAN_PACKET_SERVICE**](ns-wwan-_wwan_packet_service.md) structure.

## -see-also

[MB 5G data class support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-5g-data-class-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-packet-service)

[**WWAN_PACKET_SERVICE*](ns-wwan-_wwan_packet_service.md)
