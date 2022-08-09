---
UID: NE:iddcx.IDDCX_TRANSMISSION_TYPE
title: IDDCX_TRANSMISSION_TYPE (iddcx.h)
description: Enum used to indicate the link type for transmission of the video data.
old-location: display\iddcx_transmission_type.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_TRANSMISSION_TYPE enumeration"]
ms.keywords: IDDCX_TRANSMISSION_TYPE, IDDCX_TRANSMISSION_TYPE enumeration [Display Devices], IDDCX_TRANSMISSION_TYPE_OTHER, IDDCX_TRANSMISSION_TYPE_UNINITIALIZED, IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST, IDDCX_TRANSMISSION_TYPE_WIRED_OTHER, IDDCX_TRANSMISSION_TYPE_WIRED_USB, IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB, IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST, IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER, IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER, IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER, display.iddcx_transmission_type, iddcx/IDDCX_TRANSMISSION_TYPE, iddcx/IDDCX_TRANSMISSION_TYPE_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_UNINITIALIZED, iddcx/IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST, iddcx/IDDCX_TRANSMISSION_TYPE_WIRED_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRED_USB, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - IDDCX_TRANSMISSION_TYPE
 - iddcx/IDDCX_TRANSMISSION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_TRANSMISSION_TYPE
---

# IDDCX_TRANSMISSION_TYPE enumeration

## -description

A **IDDCX_TRANSMISSION_TYPE** value is used to indicate the link type for transmission of the video data.

## -enum-fields

### -field IDDCX_TRANSMISSION_TYPE_UNINITIALIZED:0

Indicates that an **IDDCX_TRANSMISSION_TYPE** variable has not yet been assigned a meaningful value.

### -field IDDCX_TRANSMISSION_TYPE_WIRED_USB:0x1

Video data is being transmitted over wired USB.

### -field IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST:0x2

Video data is being transmitted over a wired Miracast link.

### -field IDDCX_TRANSMISSION_TYPE_WIRED_OTHER:0x3

Video data is being transmitted over a wired connect not already described.

### -field IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB:0x4

Video data is being transmitted over wireless MA-USB.

### -field IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER:0x5

Video data is being transmitted over wireless network not using MA-USB but the device is enumerated on the USB bus.

### -field IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER:0x6

Video data is being transmitted over a WiFi wireless network.

### -field IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST:0x7

Video data is being transmitted over a wireless Miracast link.

### -field IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER:0x8

Video data is being transmitted over a non-WiFi wireless network not already described.

### -field IDDCX_TRANSMISSION_TYPE_NETWORK_OTHER:0x9

Video data is being transmitted over a TCP/UDP/IP network not already described.

### -field IDDCX_TRANSMISSION_TYPE_OTHER:0xFFFFFFFF

Video data is being transmitted over a link type that is not covered by the above definitions.

## -see-also

[**IDDCX_ENDPOINT_DIAGNOSTIC_INFO**](ns-iddcx-iddcx_endpoint_diagnostic_info.md)
