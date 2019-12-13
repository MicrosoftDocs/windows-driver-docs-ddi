---
UID: NF:netadapter.NetAdapterReportWakeReasonPacket
title: NetAdapterReportWakeReasonPacket function (netadapter.h)
author: windows-driver-content
description: The NetAdapterReportWakeReasonPacket method reports to the framework that a net adapter generated a wake-up event because it received a packet that matched a wake-on-LAN (WoL) pattern.
tech.root: netvista
ms.assetid: d37c2805-6f94-48e8-991e-0700b6b0c7fe
ms.author: windowsdriverdev
ms.date: 11/07/2019
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterReportWakeReasonPacket"
ms.keywords: NetAdapterReportWakeReasonPacket
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetAdapterReportWakeReasonPacket
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetAdapterReportWakeReasonPacket function


## -description

The **NetAdapterReportWakeReasonPacket** method reports to the framework that a net adapter generated a wake-up event because it received a packet that matched a wake-on-LAN (WoL) pattern.

## -parameters

### -param Adapter

A handle to the NETADAPTER object.

### -param Reason

A pointer to the [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure that represents the wake reason packet that the net adapter received.

## -returns

This method does not return a value.

## -remarks

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md)