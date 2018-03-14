---
UID: NA:netreceivescaling
ms.assetid: b76ca427-86f2-3158-8375-477be3d9484f
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netreceivescaling.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Netreceivescaling.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT function](nf-netreceivescaling-net_adapter_receive_scaling_capabilities_init.md) | The NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT method initializes a NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure. |
| [NetAdapterGetReceiveScalingHashSecretKey function](nf-netreceivescaling-netadaptergetreceivescalinghashsecretkey.md) | The NetAdapterGetReceiveScalingHashSecretKey method gets the receive side scaling (RSS) hash secret key for a net adapter. |
| [NetAdapterGetReceiveScalingHashType function](nf-netreceivescaling-netadaptergetreceivescalinghashtype.md) | The NetAdapterGetReceiveScalingHashType method gets the receive side scaling (RSS) hash function type for a net adapter. |
| [NetAdapterGetReceiveScalingProtocolTypes function](nf-netreceivescaling-netadaptergetreceivescalingprotocoltypes.md) | The **NetAdapterGetReceiveScalingProtocolTypes** method gets the receive side scaling (RSS) protocol types to use in hash calculations for a net adapter. |
| [NetAdapterSetReceiveScalingCapabilities function](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md) | The NetAdapterSetReceiveScalingCapabilities method sets a net adapter's receive side scaling (RSS) capabilities. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE callback function](nc-netreceivescaling-evt_net_adapter_receive_scaling_disable.md) | The EvtNetAdapterReceiveScalingEnable callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC). |
| [EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE callback function](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md) | The EvtNetAdapterReceiveScalingEnable callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC). |
| [EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY callback function](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_hash_secret_key.md) | The EvtNetAdapterReceiveScalingSetHashSecretKey callback function is implemented by the client driver to set the hash secret key for the network interface controller (NIC). |
| [EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES callback function](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md) | The EvtNetAdapterReceiveScalingSetIndirectionEntries callback function is implemented by the client driver to perform moves of individual receive side scaling (RSS) indirection table entries to new processors. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) | The NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure describes a net adapter's receive side scaling (RSS) capabilities. |
| [_NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY structure](ns-netreceivescaling-_net_adapter_receive_scaling_hash_secret_key.md) | The NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY structure contains secret key data to verify RSS hash calculations. |
| [_NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md) | The NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure represents a series of move operations for all entries in the receive side scaling (RSS) indirection table. |
| [_NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md) | The NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure represents a single entry in the receive side scaling (RSS) indirection table. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE enumeration](ne-netreceivescaling-_net_adapter_receive_scaling_encapsulation_type.md) | The NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE enumeration specifies packet encapsulation technologies an RSS-capable NIC is able to bypass. |
| [_NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE enumeration](ne-netreceivescaling-_net_adapter_receive_scaling_hash_type.md) | The NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE enumeration specifies the type of receive side scaling (RSS) hash function that a NIC should use to compute the hash values for incoming packets. |
| [_NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration](ne-netreceivescaling-_net_adapter_receive_scaling_protocol_type.md) | The NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration specifies the portion of received network data that a NIC must use to calculate an RSS hash value. |
| [_NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration](ne-netreceivescaling-_net_adapter_receive_scaling_unhashed_target_type.md) | The NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration specifies how a net adapter handles unhashed receive side scaling (RSS) frames. |
