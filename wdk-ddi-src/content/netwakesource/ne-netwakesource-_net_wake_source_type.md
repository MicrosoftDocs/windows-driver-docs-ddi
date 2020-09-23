---
UID: NE:netwakesource._NET_WAKE_SOURCE_TYPE
title: NET_WAKE_SOURCE_TYPE (netwakesource.h)
description: The NET_WAKE_SOURCE_TYPE enumeration specifies the type of a wake-on-LAN (WoL) wake-up event for a net adapter.
tech.root: netvista
ms.assetid: 70ebee95-c44c-4db8-b5ea-71b5e1236a7c
ms.date: 10/04/2019
keywords: ["NET_WAKE_SOURCE_TYPE enumeration"]
ms.keywords: NET_WAKE_SOURCE_TYPE, NET_WAKE_SOURCE_TYPE,
req.header: netwakesource.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_WAKE_SOURCE_TYPE
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_WAKE_SOURCE_TYPE
 - netwakesource/_NET_WAKE_SOURCE_TYPE
 - NET_WAKE_SOURCE_TYPE
 - netwakesource/NET_WAKE_SOURCE_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netwakesource.h
api_name:
 - NET_WAKE_SOURCE_TYPE
product:
 - Windows
---

# NET_WAKE_SOURCE_TYPE enumeration


## -description

The **NET_WAKE_SOURCE_TYPE** enumeration specifies the type for the source of a wake-on-LAN (WoL) wake-up event from a net adapter.

## -enum-fields

### -field NetWakeSourceTypeBitmapPattern 

The wake source is a bitmap pattern.

### -field NetWakeSourceTypeMagicPacket 

The wake source is a magic packet, which is a special packet that contains 16 contiguous copies of the receiving net adapter's Ethernet address.

### -field NetWakeSourceTypeMediaChange 

The wake source is a media connect or disconnect event.

### -field NetWakeSourceTypePacketFilterMatch 

The wake source is a packet that matches a filter the driver supports, such as an Ethernet unicast frame.

## -remarks

Call [**NetWakeSourceGetType**](../netwakesource/nf-netwakesource-netwakesourcegettype.md) to get the type for a WoL source.

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NetWakeSourceGetType**](../netwakesource/nf-netwakesource-netwakesourcegettype.md)