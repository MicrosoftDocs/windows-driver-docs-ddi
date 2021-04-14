---
UID: NE:netadapter._NET_ADAPTER_WAKE_PATTERN_ID
tech.root: netvista
title: NET_ADAPTER_WAKE_PATTERN_ID
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NET_ADAPTER_WAKE_PATTERN_ID is used to specify the wake pattern ID in the NET_ADAPTER_WAKE_REASON_PACKET structure.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_WAKE_PATTERN_ID
 - NET_ADAPTER_WAKE_PATTERN_ID
f1_keywords:
 - _NET_ADAPTER_WAKE_PATTERN_ID
 - netadapter/_NET_ADAPTER_WAKE_PATTERN_ID
 - NET_ADAPTER_WAKE_PATTERN_ID
 - netadapter/NET_ADAPTER_WAKE_PATTERN_ID
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_WAKE_PATTERN_ID** enumeration specifies the wake pattern ID in the [**NET_ADAPTER_WAKE_REASON_PACKET**](ns-netadapter-_net_adapter_wake_reason_packet.md) structure.

## -enum-fields

### -field NetAdapterWakeMagicPatternId


### -field NetAdapterWakeEapolPatternId


### -field NetAdapterWakeFilterPatternId


## -remarks

See [**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md) for descriptions of each wake source type.

An initialized [**NET_ADAPTER_WAKE_REASON_PACKET**](ns-netadapter-_net_adapter_wake_reason_packet.md) structure is an input to [**NetAdapterReportWakeReasonPacket**](nf-netadapter-netadapterreportwakereasonpacket.md).

## -see-also

[**NET_ADAPTER_WAKE_REASON_PACKET**](ns-netadapter-_net_adapter_wake_reason_packet.md)

[**NetAdapterReportWakeReasonPacket**](nf-netadapter-netadapterreportwakereasonpacket.md)