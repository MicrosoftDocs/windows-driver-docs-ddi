---
UID: NS:dot11wificxintf._WDI_MAC_ADDRESS
tech.root: netvista
title: WDI_MAC_ADDRESS (dot11wificxintf.h)
ms.date: 06/17/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_MAC_ADDRESS structure defines an IEEE media access control (MAC) address.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxintf.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_MAC_ADDRESS, *PWDI_MAC_ADDRESS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxintf.h
api_name:
 - _WDI_MAC_ADDRESS
 - PWDI_MAC_ADDRESS
 - WDI_MAC_ADDRESS
f1_keywords:
 - _WDI_MAC_ADDRESS
 - dot11wificxintf/_WDI_MAC_ADDRESS
 - PWDI_MAC_ADDRESS
 - dot11wificxintf/PWDI_MAC_ADDRESS
 - WDI_MAC_ADDRESS
 - dot11wificxintf/WDI_MAC_ADDRESS
dev_langs:
 - c++
---

## -description

The **WDI_MAC_ADDRESS** structure defines an IEEE media access control (MAC) address.

## -struct-fields

### -field Address

A Wi-Fi MAC address.

## -remarks

The **WDI_MAC_ADDRESS** structure is a parameter of the [WDI_TLV_BSSID](/windows-hardware/drivers/netcx/wdi-tlv-bssid) and [WDI_TLV_HESSID](/windows-hardware/drivers/netcx/wdi-tlv-hessid) TLVs.

## -see-also

[WDI_TLV_BSSID](/windows-hardware/drivers/netcx/wdi-tlv-bssid)

[WDI_TLV_HESSID](/windows-hardware/drivers/netcx/wdi-tlv-hessid)
