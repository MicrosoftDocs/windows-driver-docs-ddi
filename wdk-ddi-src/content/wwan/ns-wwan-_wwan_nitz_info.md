---
UID: NS:wwan._WWAN_NITZ_INFO
title: _WWAN_NITZ_INFO (wwan.h)
description: The WWAN_NITZ_INFO structure describes the current network time and time zone information.  
tech.root: netvista
ms.assetid: 55764A9D-388B-4ACE-9CC3-C621D5ADFBD2
ms.date: 04/11/2019
keywords: ["_WWAN_NITZ_INFO structure"]
f1_keywords:
 - "wwan/_WWAN_NITZ_INFO"
 - "_WWAN_NITZ_INFO"
ms.keywords: _WWAN_NITZ_INFO, WWAN_NITZ_INFO, *PWWAN_NITZ_INFO, 
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
req.typenames: WWAN_NITZ_INFO, *PWWAN_NITZ_INFO
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name:  
- _WWAN_NITZ_INFO
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_NITZ_INFO structure

## -description

The **WWAN_NITZ_INFO** structure describes the current network time and time zone information.  

## -struct-fields

### -field Year

The year as an integer. For example, **2014**.

### -field Month

The month, \[1-12\], where January == **1**.

### -field Day

The day of the month, \[1-31\].

### -field Hour

The hour, \[0-23\].

### -field Minute

The minute, \[0-59\].

### -field Second

The second, \[0-59\].

### -field TimeZoneOffsetMinutes

The time zone offset, in minutes, from UTC. This value includes any adjustment for the current state of daylight saving time. This value should be set to **0xFFFFFFFF** when time zone info is not available.

### -field DaylightSavingTimeOffsetMinutes

The offset for daylight saving time, in minutes. This value should be set to **0xFFFFFFFF** when daylight saving time is not available.

### -field DataClasses

Data classes supported by this network. If this information is not available, this field should be set to **WwanDataClassNone**.

## -remarks

This structure is used in the [**NDIS_WWAN_NITZ_INFO**](../ndiswwan/ns-ndiswwan-_ndis_wwan_nitz_info.md) structure.

## -see-also

[MB NITZ support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-nitz-support)

[OID_WWAN_NITZ](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-nitz)

[**NDIS_WWAN_NITZ_INFO**](../ndiswwan/ns-ndiswwan-_ndis_wwan_nitz_info.md)
