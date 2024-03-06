---
UID: NF:netadapter.NetAdapterReportWakeReasonPacket
title: NetAdapterReportWakeReasonPacket function (netadapter.h)
description: The NetAdapterReportWakeReasonPacket function reports to the framework that a net adapter generated a wake-up event because it received a packet that matched a wake-on-LAN (WoL) pattern.
tech.root: netvista
ms.date: 03/30/2022
keywords: ["NetAdapterReportWakeReasonPacket function"]
ms.keywords: NetAdapterReportWakeReasonPacket
req.header: netadapter.h
req.include-header: netadaptercx.h 
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetAdapterReportWakeReasonPacket
 - netadapter/NetAdapterReportWakeReasonPacket
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterReportWakeReasonPacket
---

# NetAdapterReportWakeReasonPacket function


## -description

The **NetAdapterReportWakeReasonPacket** function reports to the framework that a net adapter generated a wake-up event because it received a packet that matched a wake-on-LAN (WoL) pattern.

## -parameters

### -param Adapter [_In_]

A handle to the NETADAPTER object.

### -param Reason [_In_]

A pointer to the [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure that represents the wake reason packet that the net adapter received.

## -remarks

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md)
