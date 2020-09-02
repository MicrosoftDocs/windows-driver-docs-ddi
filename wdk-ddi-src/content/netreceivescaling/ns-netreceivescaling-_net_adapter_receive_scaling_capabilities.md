---
UID: NS:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
title: _NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure describes a net adapter's receive side scaling (RSS) capabilities.
tech.root: netvista
ms.assetid: d6076d3f-2f62-4b81-88b1-801e1612a28c
ms.date: 07/13/2018
keywords: ["NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure"]
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES, NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES,
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
targetos: Windows
f1_keywords:
 - _NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
 - netreceivescaling/_NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
 - NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
 - netreceivescaling/NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netreceivescaling.h
api_name:
 - _NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES
---

# _NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure


## -description

The **NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES** structure describes a net adapter's receive side scaling (RSS) capabilities.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field NumberOfQueues

The number of hardware receive queues. This member must be a power of 2.

### -field IndirectionTableSize

The number of indirection table entries. This member must be a power of 2.

### -field UnhashedTargetIndex

The default destination for frames to which no hash is applied. The value of this member depends on the value of the **UnhashedTargetType** member:

- If **UnhashedTargetType** is set to **NetAdapterReceiveScalingUnhashedTargetTypeUnspecified**, **UnhashedTarget** is ignored.
- If **UnhashedTargetType** is set to **NetAdapterReceiveScalingUnhashedTargetTypeHashIndex**, **UnhashedTarget** specifies a hash index in the indirection table.

This member must be **N**, where `0 <= N < IndirectionTableSize`.

### -field UnhashedTargetType

A [NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_unhashed_target_type.md) value that indicates the type of handling for unhashed frames. 

If this member is set to **NetAdapterReceiveScalingUnhashedTargetTypeUnspecified**, then **UnhashedTargetIndex** is ignored and defaults to **0**. 

If this member is set to **NetAdapterReceiveScalingUnhashedTargetTypeHashIndex**, then **UnhashedTargetIndex** indicates the target hash value.

### -field ReceiveScalingHashTypes

A [NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_hash_type.md) value that indicates supported hash function types for calculating hash values.

### -field ReceiveScalingProtocolTypes

A [NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_protocol_type.md) value that indicates the supported protocol types for calculating hash values.

### -field _RECEIEVE_SCALING_ENCAPSULATION

The tag identifier for **ReceiveScalingEncapsulationTypes**.

### -field ReceiveScalingEncapsulationTypes

Indicates which encapsulation technologies the hardware is capable of bypassing.

### -field ReceiveScalingEncapsulationTypes.Outer

A bitwise OR of [NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_encapsulation_type.md) values that indicates the transport (outer) encapsulation types that the NIC is capable of bypassing.

### -field ReceiveScalingEncapsulationTypes.Inner

A bitwise OR of [NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_encapsulation_type.md) values that indicates the tunnel (inner) encapsulation types that the NIC is capable of bypassing.

### -field SynchronizeSetIndirectionEntries

A boolean value that, when set to **TRUE**, requests that the framework synchronize calls to *[EvtNetAdapterReceiveScalingSetIndirectionEntries](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md)*. This member is set to **FALSE** by default if the client driver does not specify it.

### -field EvtAdapterReceiveScalingEnable

A pointer to the client driver's *[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)* event callback function.

### -field EvtAdapterReceiveScalingDisable

A pointer to the client driver's *[EvtNetAdapterReceiveScalingDisable](nc-netreceivescaling-evt_net_adapter_receive_scaling_disable.md)* event callback function.

### -field EvtAdapterReceiveScalingSetHashSecretKey

A pointer to the client driver's *[EvtNetAdapterReceiveScalingSetHashSecretKey](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_hash_secret_key.md)* event callback function.

### -field EvtAdapterReceiveScalingSetIndirectionEntries

A pointer to the client driver's *[EvtNetAdapterReceiveScalingSetIndirectionEntries](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md)* event callback function.

## -remarks

Call [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT](nf-netreceivescaling-net_adapter_receive_scaling_capabilities_init.md) to initialize this structure.

The **NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES** structure is an input parameter to [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). The client must use [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT](nf-netreceivescaling-net_adapter_receive_scaling_capabilities_init.md) to initialize this structure before calling **NetAdapterSetReceiveScalingCapabilities**.

## -see-also

[NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT](nf-netreceivescaling-net_adapter_receive_scaling_capabilities_init.md)

[NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)

