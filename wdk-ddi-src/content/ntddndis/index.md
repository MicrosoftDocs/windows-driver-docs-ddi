---
UID: NA:ntddndis
ms.assetid: 3070c304-be06-3c47-8296-026e9700c955
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddndis.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Ntddndis.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD structure](ns-ntddndis-_ndis_encapsulated_packet_task_offload.md) | The NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD structure contains the offload support state for Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload (NVGRE-TO). |
| [_NDIS_HD_SPLIT_CURRENT_CONFIG structure](ns-ntddndis-_ndis_hd_split_current_config.md) | The NDIS_HD_SPLIT_CURRENT_CONFIG structure provides the current header-data split configuration of a miniport adapter. |
| [_NDIS_HD_SPLIT_PARAMETERS structure](ns-ntddndis-_ndis_hd_split_parameters.md) | The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport adapter. |
| [_NDIS_HYPERVISOR_INFO structure](ns-ntddndis-_ndis_hypervisor_info.md) | The NDIS_HYPERVISOR_INFO structure contains information about the hypervisor that is present on the system. |
| [_NDIS_INTERRUPT_MODERATION_PARAMETERS structure](ns-ntddndis-_ndis_interrupt_moderation_parameters.md) | The NDIS_INTERRUPT_MODERATION_PARAMETERS structure defines interrupt parameters for the OID_GEN_INTERRUPT_MODERATION OID. |
| [_NDIS_IPSEC_OFFLOAD_V1 structure](ns-ntddndis-_ndis_ipsec_offload_v1.md) | The NDIS_IPSEC_OFFLOAD_V1 structure provides Internet protocol security (IPsec) task offload information in the NDIS_OFFLOAD structure.Note  NDIS_IPSEC_OFFLOAD_V1 is only for NDIS 6.0. |
| [_NDIS_IPSEC_OFFLOAD_V2 structure](ns-ntddndis-_ndis_ipsec_offload_v2.md) | The NDIS_IPSEC_OFFLOAD_V2 structure provides information about Internet protocol security (IPsec) version 2 task offload capabilities in the NDIS_OFFLOAD structure. |
| [_NDIS_ISOLATION_NAME structure](ns-ntddndis-_ndis_isolation_name.md) | The NDIS_ISOLATION_NAME structure contains an NDIS isolation name for a VM network adapter. |
| [_NDIS_ISOLATION_PARAMETERS structure](ns-ntddndis-_ndis_isolation_parameters.md) | The NDIS_ISOLATION_PARAMETERS structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return the isolation parameters that are set on a VM network adapter's port. |
| [_NDIS_LINK_SPEED structure](ns-ntddndis-_ndis_link_speed.md) | The NDIS_LINK_SPEED structure specifies transmit and receive link speeds. |
| [_NDIS_LINK_STATE structure](ns-ntddndis-_ndis_link_state.md) | The NDIS_LINK_STATE structure specifies the current link state of a miniport adapter. |
| [_NDIS_NDK_CAPABILITIES structure](ns-ntddndis-_ndis_ndk_capabilities.md) | The NDIS_NDK_CAPABILITIES structure specifies the capabilities of an NDK adapter. |
| [_NDIS_NDK_CONNECTIONS structure](ns-ntddndis-_ndis_ndk_connections.md) | The NDIS_NDK_CONNECTIONS structure describes the NDK connections that are active on a miniport adapter. |
| [_NDIS_NDK_CONNECTION_ENTRY structure](ns-ntddndis-_ndis_ndk_connection_entry.md) | The NDIS_NDK_CONNECTION_ENTRY structure specifies a connection entry for an active NDK connection on a miniport adapter. |
| [_NDIS_NDK_LOCAL_ENDPOINTS structure](ns-ntddndis-_ndis_ndk_local_endpoints.md) | The NDIS_NDK_LOCAL_ENDPOINTS structure describes the NDK local endpoints that are on a miniport adapter. |
| [_NDIS_NDK_LOCAL_ENDPOINT_ENTRY structure](ns-ntddndis-_ndis_ndk_local_endpoint_entry.md) | The NDIS_NDK_LOCAL_ENDPOINT_ENTRY structure specifies an ND local endpoint entry for an ND local endpoint on a miniport adapter. |
| [_NDIS_NDK_PERFORMANCE_COUNTERS structure](ns-ntddndis-_ndis_ndk_performance_counters.md) | The NDIS_NDK_PERFORMANCE_COUNTERS structure contains the NDK performance counters. |
| [_NDIS_NDK_STATISTICS_INFO structure](ns-ntddndis-_ndis_ndk_statistics_info.md) | The NDIS_NDK_STATISTICS_INFO structure contains the NDK statistics. |
| [_NDIS_NIC_SWITCH_CAPABILITIES structure](ns-ntddndis-_ndis_nic_switch_capabilities.md) | The NDIS_NIC_SWITCH_CAPABILITIES structure specifies the capabilities of a NIC switch on the network adapter. |
| [_NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS structure](ns-ntddndis-_ndis_nic_switch_delete_switch_parameters.md) | The NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS structure specifies the information about the network adapter switch that will be deleted from the network adapter. |
| [_NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS structure](ns-ntddndis-_ndis_nic_switch_delete_vport_parameters.md) | The NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS structure specifies the information about a virtual port (VPort) that will be deleted from a network adapter switch on the network adapter. |
| [_NDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure](ns-ntddndis-_ndis_nic_switch_free_vf_parameters.md) | The NDIS_NIC_SWITCH_FREE_VF_PARAMETERS specifies a PCI Express (PCIe) Virtual Function (VF) whose resources will be freed. |
| [_NDIS_NIC_SWITCH_INFO structure](ns-ntddndis-_ndis_nic_switch_info.md) | The NDIS_NIC_SWITCH_INFO structure specifies the information about a network adapter switch on a network adapter. |
| [_NDIS_NIC_SWITCH_INFO_ARRAY structure](ns-ntddndis-_ndis_nic_switch_info_array.md) | The NDIS_NIC_SWITCH_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a network adapter switch that has been created on the network adapter. |
| [_NDIS_NIC_SWITCH_PARAMETERS structure](ns-ntddndis-_ndis_nic_switch_parameters.md) | The NDIS_NIC_SWITCH_PARAMETERS structure specifies the configuration parameters of a network adapter switch on the network adapter. |
| [_NDIS_NIC_SWITCH_VF_INFO structure](ns-ntddndis-_ndis_nic_switch_vf_info.md) | The NDIS_NIC_SWITCH_VF_INFO structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter. |
| [_NDIS_NIC_SWITCH_VF_INFO_ARRAY structure](ns-ntddndis-_ndis_nic_switch_vf_info_array.md) | The NDIS_NIC_SWITCH_VF_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter. |
| [_NDIS_NIC_SWITCH_VF_PARAMETERS structure](ns-ntddndis-_ndis_nic_switch_vf_parameters.md) | The NDIS_NIC_SWITCH_VF_PARAMETERS specifies the resource parameters of a PCI Express (PCIe) Virtual Function (VF) on a network adapter. |
| [_NDIS_NIC_SWITCH_VPORT_INFO structure](ns-ntddndis-_ndis_nic_switch_vport_info.md) | The NDIS_NIC_SWITCH_VPORT_INFO structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter. |
| [_NDIS_NIC_SWITCH_VPORT_INFO_ARRAY structure](ns-ntddndis-_ndis_nic_switch_vport_info_array.md) | The NDIS_NIC_SWITCH_VPORT_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a virtual port (VPort) that has been created on a network adapter's network adapter switch. |
| [_NDIS_NIC_SWITCH_VPORT_PARAMETERS structure](ns-ntddndis-_ndis_nic_switch_vport_parameters.md) | The NDIS_NIC_SWITCH_VPORT_PARAMETERS structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter. |
| [_NDIS_OBJECT_HEADER structure](ns-ntddndis-_ndis_object_header.md) | The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is required in many NDIS 6.0 structures. |
| [_NDIS_OFFLOAD structure](ns-ntddndis-_ndis_offload.md) | The NDIS_OFFLOAD structure specifies several computational tasks that can be offloaded to the network adapter. |
| [_NDIS_OFFLOAD_PARAMETERS structure](ns-ntddndis-_ndis_offload_parameters.md) | The NDIS_OFFLOAD_PARAMETERS structure specifies the current task offload configuration settings in response to an OID set request of OID_TCP_OFFLOAD_PARAMETERS. |
| [_NDIS_OPER_STATE structure](ns-ntddndis-_ndis_oper_state.md) | The NDIS_OPER_STATE structure provides the current operational state of an NDIS network interface. |
| [_NDIS_PCI_DEVICE_CUSTOM_PROPERTIES structure](ns-ntddndis-_ndis_pci_device_custom_properties.md) | The NDIS_PCI_DEVICE_CUSTOM_PROPERTIES structure defines the type and speed of the PCI bus that a NIC is running on. |
| [_NDIS_PD_CAPABILITIES structure](ns-ntddndis-_ndis_pd_capabilities.md) | This structure indicates the PD capabilities for a provider. |
| [_NDIS_PD_CONFIG structure](ns-ntddndis-_ndis_pd_config.md) | This structure holds configuration data for the PD provider. |
| [_NDIS_PM_CAPABILITIES structure](ns-ntddndis-_ndis_pm_capabilities.md) | The NDIS_PM_CAPABILITIES structure specifies power management capabilities of a network adapter. |
| [_NDIS_PM_COUNTED_STRING structure](ns-ntddndis-_ndis_pm_counted_string.md) | The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management structures. |
| [_NDIS_PM_PACKET_PATTERN structure](ns-ntddndis-_ndis_pm_packet_pattern.md) | The NDIS_PM_PACKET_PATTERN structure specifies a wake-up pattern, which, when detected by a network adapter that has pattern-match enabled, causes the network adapter to signal a power-management wake-up event. |
| [_NDIS_PM_PARAMETERS structure](ns-ntddndis-_ndis_pm_parameters.md) | The NDIS_PM_PARAMETERS structure specifies the current or new power management hardware capabilities that are enabled for a network adapter. |
| [_NDIS_PM_PROTOCOL_OFFLOAD structure](ns-ntddndis-_ndis_pm_protocol_offload.md) | The NDIS_PM_PROTOCOL_OFFLOAD structure specifies parameters for a low power protocol offload to a network adapter. |
| [_NDIS_PM_WAKE_PACKET structure](ns-ntddndis-_ndis_pm_wake_packet.md) | The NDIS_PM_WAKE_PACKET structure describes a network packet (known as a wake packet) that caused the network adapter to generate a wake-up event. |
| [_NDIS_PM_WAKE_REASON structure](ns-ntddndis-_ndis_pm_wake_reason.md) | The NDIS_PM_WAKE_REASON structure specifies information about the wake-up event that was generated by a network adapter. |
| [_NDIS_PM_WOL_PATTERN structure](ns-ntddndis-_ndis_pm_wol_pattern.md) | The NDIS_PM_WOL_PATTERN structure defines a wake-on-LAN (WOL) pattern. |
| [_NDIS_PORT structure](ns-ntddndis-_ndis_port.md) | The NDIS_PORT structure specifies the characteristics of an NDIS port and a pointer to the next element in a linked list of ports. |
| [_NDIS_PORT_ARRAY structure](ns-ntddndis-_ndis_port_array.md) | The NDIS_PORT_ARRAY structure specifies a list of NDIS ports and their associated characteristics. |
| [_NDIS_PORT_AUTHENTICATION_PARAMETERS structure](ns-ntddndis-_ndis_port_authentication_parameters.md) | The NDIS_PORT_AUTHENTICATION_PARAMETERS structure specifies the state parameters for an NDIS port. |
| [_NDIS_PORT_CHARACTERISTICS structure](ns-ntddndis-_ndis_port_characteristics.md) | The NDIS_PORT_CHARACTERISTICS structure specifies the characteristics of an NDIS port. For more information about NDIS ports, see NDIS Ports. |
| [_NDIS_PORT_STATE structure](ns-ntddndis-_ndis_port_state.md) | The NDIS_PORT_STATE structure specifies the port state information for an NDIS port. |
| [_NDIS_PROCESSOR_INFO_EX structure](ns-ntddndis-_ndis_processor_info_ex.md) | The NDIS_PROCESSOR_INFO_EX structure specifies information about a processor in the local computer. |
| [_NDIS_QOS_CAPABILITIES structure](ns-ntddndis-_ndis_qos_capabilities.md) | The NDIS_QOS_CAPABILITIES structure specifies the NDIS Quality of Service (QoS) capabilities of a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface. |
| [_NDIS_QOS_CLASSIFICATION_ELEMENT structure](ns-ntddndis-_ndis_qos_classification_element.md) | The NDIS_QOS_CLASSIFICATION_ELEMENT structure specifies an NDIS Quality of Service (QoS) traffic classification for a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.Each traffic classification specifies the following |
| [_NDIS_QOS_PARAMETERS structure](ns-ntddndis-_ndis_qos_parameters.md) | The NDIS_QOS_PARAMETERS structure specifies the NDIS Quality of Service (QoS) parameters that are enabled on a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface. |
| [_NDIS_RECEIVE_FILTER_CAPABILITIES structure](ns-ntddndis-_ndis_receive_filter_capabilities.md) | The NDIS_RECEIVE_FILTER_CAPABILITIES structure specifies the receive filtering capabilities of a network adapter. |
| [_NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure](ns-ntddndis-_ndis_receive_filter_clear_parameters.md) | The NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure specifies the parameters to clear a receive filter on a network adapter. |
| [_NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure](ns-ntddndis-_ndis_receive_filter_field_parameters.md) | The NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure specifies the filter test criterion for a field in a network packet header. |
| [_NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure](ns-ntddndis-_ndis_receive_filter_global_parameters.md) | The NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure specifies the receive filtering features that are enabled or disabled on a network adapter.NDIS receive filters are used in the following NDIS interfaces |
| [_NDIS_RECEIVE_FILTER_INFO structure](ns-ntddndis-_ndis_receive_filter_info.md) | The NDIS_RECEIVE_FILTER_INFO structure contains information about a receive filter that is currently configured on a miniport driver. |
| [_NDIS_RECEIVE_FILTER_INFO_ARRAY structure](ns-ntddndis-_ndis_receive_filter_info_array.md) | The NDIS_RECEIVE_FILTER_INFO_ARRAY structure specifies a list of receive filters that are currently configured on a miniport driver. |
| [_NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure](ns-ntddndis-_ndis_receive_filter_move_filter_parameters.md) | The NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure specifies the parameters for moving a previously created receive filter. A receive filter is moved from a receive queue on a virtual port (VPort) to a receive queue on another VPort. |
| [_NDIS_RECEIVE_FILTER_PARAMETERS structure](ns-ntddndis-_ndis_receive_filter_parameters.md) | The NDIS_RECEIVE_FILTER_PARAMETERS structure specifies the parameters for an NDIS receive filter. |
| [_NDIS_RECEIVE_HASH_PARAMETERS structure](ns-ntddndis-_ndis_receive_hash_parameters.md) | The NDIS_RECEIVE_HASH_PARAMETERS structure specifies the receive hash parameters for a miniport adapter that supports receive hash calculations. |
| [_NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure](ns-ntddndis-_ndis_receive_queue_allocation_complete_array.md) | The NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure contains information about the allocation status of a batch of receive queues. |
| [_NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure](ns-ntddndis-_ndis_receive_queue_allocation_complete_parameters.md) | The NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure contains information about the allocation status of a receive queue. |
| [_NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure](ns-ntddndis-_ndis_receive_queue_free_parameters.md) | The NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure identifies a receive queue to free. |
| [_NDIS_RECEIVE_QUEUE_INFO structure](ns-ntddndis-_ndis_receive_queue_info.md) | The NDIS_RECEIVE_QUEUE_INFO structure contains information about a receive queue on a network adapter. |
| [_NDIS_RECEIVE_QUEUE_INFO_ARRAY structure](ns-ntddndis-_ndis_receive_queue_info_array.md) | The NDIS_RECEIVE_QUEUE_INFO_ARRAY structure specifies a list of receive queues on a network adapter. |
| [_NDIS_RECEIVE_QUEUE_PARAMETERS structure](ns-ntddndis-_ndis_receive_queue_parameters.md) | The NDIS_RECEIVE_QUEUE_PARAMETERS structure contains the configuration parameters of a receive queue. |
| [_NDIS_RECEIVE_SCALE_CAPABILITIES structure](ns-ntddndis-_ndis_receive_scale_capabilities.md) | The NDIS_RECEIVE_SCALE_CAPABILITIES structure specifies the receive side scaling (RSS) capabilities of a miniport adapter. |
| [_NDIS_RECEIVE_SCALE_PARAMETERS structure](ns-ntddndis-_ndis_receive_scale_parameters.md) | The NDIS_RECEIVE_SCALE_PARAMETERS structure specifies the receive side scaling (RSS) parameters for a miniport adapter. |
| [_NDIS_RECEIVE_SCALE_PARAMETERS_V2 structure](ns-ntddndis-_ndis_receive_scale_parameters_v2.md) | The NDIS_RECEIVE_SCALE_PARAMETERS_V2 structure specifies the Receive Side Scaling (RSS) parameters for a miniport adapter that advertises support for RSS Version 2 (RSSv2). It is used in the OID_GEN_RECEIVE_SCALE_PARAMETERS_V2 RSSv2 OID. |
| [_NDIS_ROUTING_DOMAIN_ENTRY structure](ns-ntddndis-_ndis_routing_domain_entry.md) | The NDIS_ROUTING_DOMAIN_ENTRY structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return the routing domain entries for a VM network adapter's port. |
| [_NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure](ns-ntddndis-_ndis_routing_domain_isolation_entry.md) | The NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return information relating to a single isolation ID within a routing domain entry for a Hyper-V extensible switch network adapter's port. |
| [_NDIS_RSC_STATISTICS_INFO structure](ns-ntddndis-_ndis_rsc_statistics_info.md) | The NDIS_RSC_STATISTICS_INFO structure contains statistics that a miniport driver supplies in response to a query of the OID_TCP_RSC_STATISTICS OID. |
| [_NDIS_RSS_PROCESSOR structure](ns-ntddndis-_ndis_rss_processor.md) | The NDIS_RSS_PROCESSOR structure specifies information about a processor in the local computer for receive side scaling (RSS). |
| [_NDIS_RSS_PROCESSOR_INFO structure](ns-ntddndis-_ndis_rss_processor_info.md) | The NDIS_RSS_PROCESSOR_INFO structure specifies information about the CPU receive side scaling (RSS) processor set on the local computer. |
| [_NDIS_RSS_SET_INDIRECTION_ENTRIES structure](ns-ntddndis-_ndis_rss_set_indirection_entries.md) | The NDIS_RSS_SET_INDIRECTION_ENTRIES structure represents a set of actions, where each action moves a single entry of the Receive Side Scaling (RSS) indirection table of a specified VPort to a specified target CPU. |
| [_NDIS_RSS_SET_INDIRECTION_ENTRY structure](ns-ntddndis-_ndis_rss_set_indirection_entry.md) | The NDIS_RSS_SET_INDIRECTION_ENTRY structure represents a command to set a single indirection table entry. |
| [_NDIS_SRIOV_BAR_RESOURCES_INFO structure](ns-ntddndis-_ndis_sriov_bar_resources_info.md) | The NDIS_SRIOV_BAR_RESOURCES_INFO structure specifies the PCI Express (PCIe) Base Address Register (BAR) of a network adapter's PCIe Virtual Function (VF). |
| [_NDIS_SRIOV_CAPABILITIES structure](ns-ntddndis-_ndis_sriov_capabilities.md) | The NDIS_SRIOV_CAPABILITIES structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter. |
| [_NDIS_SRIOV_PF_LUID_INFO structure](ns-ntddndis-_ndis_sriov_pf_luid_info.md) | The NDIS_SRIOV_PF_LUID_INFO structure specifies the locally unique identifier (LUID) associated with the network adapter's PCI Express (PCIe) Physical Function (PF). |
| [_NDIS_SRIOV_PROBED_BARS_INFO structure](ns-ntddndis-_ndis_sriov_probed_bars_info.md) | The NDIS_SRIOV_PROBED_BARS_INFO structure specifies the values of the PCI Express (PCIe) Base Address Registers (BARs) of a network adapter that supports the single root I/O virtualization (SR-IOV) interface. |
| [_NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure](ns-ntddndis-_ndis_sriov_read_vf_config_block_parameters.md) | The NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure specifies the parameters for a read operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF). |
| [_NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS structure](ns-ntddndis-_ndis_sriov_read_vf_config_space_parameters.md) | The NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS structure specifies the parameters for a read operation on the PCI Express (PCIe) configuration space of a network adapter's Virtual Function (VF). |
| [_NDIS_SRIOV_RESET_VF_PARAMETERS structure](ns-ntddndis-_ndis_sriov_reset_vf_parameters.md) | The NDIS_SRIOV_RESET_VF_PARAMETERS structure specifies the parameters for resetting a network adapter's PCI Express (PCIe) Virtual Function (VF). |
| [_NDIS_SRIOV_SET_VF_POWER_STATE_PARAMETERS structure](ns-ntddndis-_ndis_sriov_set_vf_power_state_parameters.md) | The NDIS_SRIOV_SET_VF_POWER_STATE_PARAMETERS structure specifies the parameters for changing the power state of a network adapter's PCI Express (PCIe) Virtual Function (VF). |
| [_NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure](ns-ntddndis-_ndis_sriov_vf_invalidate_config_block_info.md) | The NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure specifies one or more Virtual Function (VF) configuration blocks whose data has been changed (invalidated) by the driver for the PCI Express (PCIe) Physical Function (PF) on the network adapter. |
| [_NDIS_SRIOV_VF_SERIAL_NUMBER_INFO structure](ns-ntddndis-_ndis_sriov_vf_serial_number_info.md) | The NDIS_SRIOV_VF_SERIAL_NUMBER_INFO structure contains the serial number associated with a PCI Express (PCIe) Virtual Function (VF) network adapter. This adapter is exposed in the guest operating system of a Hyper-V child partition. |
| [_NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure](ns-ntddndis-_ndis_sriov_vf_vendor_device_id_info.md) | The NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter. |
| [_NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure](ns-ntddndis-_ndis_sriov_write_vf_config_block_parameters.md) | The NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure specifies the parameters for a write operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF). |
| [_NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure](ns-ntddndis-_ndis_sriov_write_vf_config_space_parameters.md) | The NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure specifies the parameters for a write operation on the PCI Express (PCIe) configuration space of a network adapter's Virtual Function (VF). |
| [_NDIS_SWITCH_FEATURE_STATUS_CUSTOM structure](ns-ntddndis-_ndis_switch_feature_status_custom.md) | The NDIS_SWITCH_FEATURE_STATUS_CUSTOM structure specifies the custom status information for a Hyper-V extensible switch. |
| [_NDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure](ns-ntddndis-_ndis_switch_feature_status_parameters.md) | The NDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure specifies the parameters for the custom status information of a Hyper-V extensible switch. |
| [_NDIS_SWITCH_NIC_ARRAY structure](ns-ntddndis-_ndis_switch_nic_array.md) | The NDIS_SWITCH_NIC_ARRAY structure specifies an array of network adapter configuration parameters. |
| [_NDIS_SWITCH_NIC_OID_REQUEST structure](ns-ntddndis-_ndis_switch_nic_oid_request.md) | The NDIS_SWITCH_NIC_OID_REQUEST structure specifies the information that is required to forward or originate OID requests. |
| [_NDIS_SWITCH_NIC_PARAMETERS structure](ns-ntddndis-_ndis_switch_nic_parameters.md) | The NDIS_SWITCH_NIC_PARAMETERS structure specifies the configuration parameters for a network adapter (NIC) that is connected to a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_NIC_SAVE_STATE structure](ns-ntddndis-_ndis_switch_nic_save_state.md) | The NDIS_SWITCH_NIC_SAVE_STATE structure specifies the run-time state information for a Hyper-V extensible switch port. The extensible switch extension uses this structure to save or restore run-time port information. |
| [_NDIS_SWITCH_PARAMETERS structure](ns-ntddndis-_ndis_switch_parameters.md) | The NDIS_SWITCH_PARAMETERS structure contains the configuration data for a Hyper-V extensible switch. |
| [_NDIS_SWITCH_PORT_ARRAY structure](ns-ntddndis-_ndis_switch_port_array.md) | The NDIS_SWITCH_PORT_ARRAY structure specifies an array of port configuration parameters. Each element in the array specifies the parameters for a Hyper-V extensible switch port. Each element is formatted as an NDIS_SWITCH_PORT_PARAMETERS structure. |
| [_NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure](ns-ntddndis-_ndis_switch_port_feature_status_custom.md) | The NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure specifies the custom status information for a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS structure](ns-ntddndis-_ndis_switch_port_feature_status_parameters.md) | The NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS structure specifies the parameters for the custom status information of a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_PARAMETERS structure](ns-ntddndis-_ndis_switch_port_parameters.md) | The NDIS_SWITCH_PORT_PARAMETERS structure contains the configuration data for a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure](ns-ntddndis-_ndis_switch_port_property_custom.md) | The NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure specifies a custom policy property for a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS structure](ns-ntddndis-_ndis_switch_port_property_delete_parameters.md) | The NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS structure specifies the parameters for a Hyper-V extensible switch port policy property that will be deleted. |
| [_NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure](ns-ntddndis-_ndis_switch_port_property_enum_info.md) | The NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure contains information about a Hyper-V extensible switch port policy property. |
| [_NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure](ns-ntddndis-_ndis_switch_port_property_enum_parameters.md) | The NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure specifies an array of policy properties for a Hyper-V extensible switch port. Each element in the array is formatted as an NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure. |
| [_NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure](ns-ntddndis-_ndis_switch_port_property_isolation.md) | The NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure is used to specify the isolation properties for a VM network adapter's port. |
| [_NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure](ns-ntddndis-_ndis_switch_port_property_parameters.md) | The NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure specifies the parameters for a policy property of a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_PROPERTY_PROFILE structure](ns-ntddndis-_ndis_switch_port_property_profile.md) | The NDIS_SWITCH_PORT_PROPERTY_PROFILE structure specifies a policy property for a Hyper-V extensible switch port that the extensible switch extension saves in its own policy store instead of in the Hyper-V policy store. |
| [_NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure](ns-ntddndis-_ndis_switch_port_property_routing_domain.md) | The NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure is used to specify the routing domain properties of a VM network adapter. |
| [_NDIS_SWITCH_PORT_PROPERTY_SECURITY structure](ns-ntddndis-_ndis_switch_port_property_security.md) | The NDIS_SWITCH_PORT_PROPERTY_SECURITY structure specifies a security policy property for a Hyper-V extensible switch port.NDIS_SWITCH_PORT_PROPERTY_SECURITY structure specifies a security policy property for a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_PROPERTY_VLAN structure](ns-ntddndis-_ndis_switch_port_property_vlan.md) | The NDIS_SWITCH_PORT_PROPERTY_VLAN structure specifies a virtual local area network (VLAN) policy property for a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PROPERTY_CUSTOM structure](ns-ntddndis-_ndis_switch_property_custom.md) | The NDIS_SWITCH_PROPERTY_CUSTOM structure specifies a custom profile property for the Hyper-V extensible switch. Independent software vendors (ISVs) define the format for the custom properties. The format of the custom property is proprietary to the ISV. |
| [_NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure](ns-ntddndis-_ndis_switch_property_delete_parameters.md) | The NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure specifies the parameters for a Hyper-V extensible switch profile property that will be deleted. |
| [_NDIS_SWITCH_PROPERTY_ENUM_INFO structure](ns-ntddndis-_ndis_switch_property_enum_info.md) | The NDIS_SWITCH_PROPERTY_ENUM_INFO structure specifies information about a profile property for the Hyper-V extensible switch. |
| [_NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure](ns-ntddndis-_ndis_switch_property_enum_parameters.md) | The NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure specifies an array of profile properties for the Hyper-V extensible switch. Each element in the array is formatted as an NDIS_SWITCH_PROPERTY_ENUM_INFO structure. |
| [_NDIS_SWITCH_PROPERTY_PARAMETERS structure](ns-ntddndis-_ndis_switch_property_parameters.md) | The NDIS_SWITCH_PROPERTY_PARAMETERS structure specifies the parameters for a policy property of a Hyper-V extensible switch. |
| [_NDIS_SYSTEM_PROCESSOR_INFO_EX structure](ns-ntddndis-_ndis_system_processor_info_ex.md) | The NDIS_SYSTEM_PROCESSOR_INFO_EX structure specifies information about the CPU topology of the local computer. |
| [_NDIS_TCP_CONNECTION_OFFLOAD structure](ns-ntddndis-_ndis_tcp_connection_offload.md) | The NDIS_TCP_CONNECTION_OFFLOAD structure provides connection offload information for current settings and for supported capabilities. |
| [_NDIS_TCP_IP_CHECKSUM_OFFLOAD structure](ns-ntddndis-_ndis_tcp_ip_checksum_offload.md) | The NDIS_TCP_IP_CHECKSUM_OFFLOAD structure provides checksum task offload information in the NDIS_OFFLOAD structure. |
| [_NDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure](ns-ntddndis-_ndis_tcp_large_send_offload_v1.md) | The NDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure provides large send offload version 1 (LSOV1) information in the NDIS_OFFLOAD structure. |
| [_NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure](ns-ntddndis-_ndis_tcp_large_send_offload_v2.md) | The NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure provides large send offload version 2 (LSOV2) information in the NDIS_OFFLOAD structure. |
| [_NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure](ns-ntddndis-_ndis_tcp_recv_seg_coalesce_offload.md) | The NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure contains the offload support state for receive segment coalescing (RSC). |
| [_NDIS_WMI_ENUM_ADAPTER structure](ns-ntddndis-_ndis_wmi_enum_adapter.md) | The NDIS_WMI_ENUM_ADAPTER structure is returned when NDIS responds to the GUID_NDIS_ENUMERATE_ADAPTERS_EX GUID. |
| [_NDIS_WMI_EVENT_HEADER structure](ns-ntddndis-_ndis_wmi_event_header.md) | The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients. |
| [_NDIS_WMI_METHOD_HEADER structure](ns-ntddndis-_ndis_wmi_method_header.md) | The NDIS_WMI_METHOD_HEADER structure provides information about a GUID method request from WMI clients. |
| [_NDIS_WMI_SET_HEADER structure](ns-ntddndis-_ndis_wmi_set_header.md) | The NDIS_WMI_SET_HEADER structure provides information about a GUID set request from WMI clients. |
| [_OFFLOAD_ALGO_INFO structure](ns-ntddndis-_offload_algo_info.md) | The OFFLOAD_ALGO_INFO structure specifies an algorithm used for a security association (SA). |
| [_OFFLOAD_IPSEC_ADD_SA structure](ns-ntddndis-_offload_ipsec_add_sa.md) | The OFFLOAD_IPSEC_ADD_SA structure contains information for each security association (SA) that a miniport driver adds to a NIC. |
| [_OFFLOAD_IPSEC_ADD_UDPESP_SA structure](ns-ntddndis-_offload_ipsec_add_udpesp_sa.md) | The OFFLOAD_IPSEC_ADD_UDPESP_SA structure contains information for each security association (SA) that a miniport driver adds for UDP-encapsulated ESP packets to a NIC. |
| [_OFFLOAD_IPSEC_DELETE_SA structure](ns-ntddndis-_offload_ipsec_delete_sa.md) | The OFFLOAD_IPSEC_DELETE_SA structure contains information for each security association (SA) that a miniport driver deletes from a NIC. |
| [_OFFLOAD_IPSEC_DELETE_UDPESP_SA structure](ns-ntddndis-_offload_ipsec_delete_udpesp_sa.md) | The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA) and parser entry that a miniport driver deletes from a NIC. |
| [_OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure](ns-ntddndis-_offload_ipsec_udpesp_encaptype_entry.md) | The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure specifies the UDP-ESP encapsulation type and destination port of a parser entry. |
| [_OFFLOAD_SECURITY_ASSOCIATION structure](ns-ntddndis-_offload_security_association.md) | The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA). |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NDIS_ARP_HEADER_FIELD enumeration](ne-ntddndis-_ndis_arp_header_field.md) | The NDIS_ARP_HEADER_FIELD enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header. |
| [_NDIS_DEVICE_POWER_STATE enumeration](ne-ntddndis-_ndis_device_power_state.md) | The NDIS_DEVICE_POWER_STATE enumeration defines device power state values. |
| [_NDIS_FRAME_HEADER enumeration](ne-ntddndis-_ndis_frame_header.md) | The NDIS_FRAME_HEADER enumeration identifies the type of header in a network data frame. |
| [_NDIS_HYPERVISOR_PARTITION_TYPE enumeration](ne-ntddndis-_ndis_hypervisor_partition_type.md) | The NDIS_HYPERVISOR_PARTITION_TYPE enumeration identifies the current partition type that is running on the hypervisor. |
| [_NDIS_IPV4_HEADER_FIELD enumeration](ne-ntddndis-_ndis_ipv4_header_field.md) | The NDIS_IPV4_HEADER_FIELD enumeration identifies the type of a field in an IP version 4 (IPv4) header to be filtered. |
| [_NDIS_IPV6_HEADER_FIELD enumeration](ne-ntddndis-_ndis_ipv6_header_field.md) | The NDIS_IPV6_HEADER_FIELD enumeration identifies the type of a field in an IP version 6 (IPv6) header to be filtered. |
| [_NDIS_ISOLATION_MODE enumeration](ne-ntddndis-_ndis_isolation_mode.md) | The NDIS_ISOLATION_MODE enumeration defines the network isolation modes that can be specified for a VM network adapter. |
| [_NDIS_MAC_HEADER_FIELD enumeration](ne-ntddndis-_ndis_mac_header_field.md) | The NDIS_MAC_HEADER_FIELD enumeration identifies the type of a field in a media access control (MAC) header to be filtered. |
| [_NDIS_MAC_PACKET_TYPE enumeration](ne-ntddndis-_ndis_mac_packet_type.md) | The NDIS_MAC_PACKET_TYPE enumeration identifies the type of a destination address field in a media access control (MAC) header to be filtered. |
| [_NDIS_MEDIUM enumeration](ne-ntddndis-_ndis_medium.md) | The NDIS_MEDIUM enumeration type identifies the medium types that NDIS drivers support. |
| [_NDIS_NIC_SWITCH_TYPE enumeration](ne-ntddndis-_ndis_nic_switch_type.md) | The NDIS_NIC_SWITCH_TYPE enumeration specifies the type of the NIC switch on a network adapter. |
| [_NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration](ne-ntddndis-_ndis_nic_switch_vport_interrupt_moderation.md) | The NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch. |
| [_NDIS_NIC_SWITCH_VPORT_STATE enumeration](ne-ntddndis-_ndis_nic_switch_vport_state.md) | The NDIS_NIC_SWITCH_VPORT_STATE enumeration specifies the state of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch of a network adapter. |
| [_NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration](ne-ntddndis-_ndis_pm_protocol_offload_type.md) | The NDIS_PM_PROTOCOL_OFFLOAD_TYPE enumeration identifies the type of a protocol offload for NDIS network adapter power management. |
| [_NDIS_PM_WAKE_REASON_TYPE enumeration](ne-ntddndis-_ndis_pm_wake_reason_type.md) | The NDIS_PM_WAKE_REASON_TYPE enumeration identifies the type of wake-up event that was generated by the network adapter. |
| [_NDIS_PM_WOL_PACKET enumeration](ne-ntddndis-_ndis_pm_wol_packet.md) | The NDIS_PM_WOL_PACKET enumeration identifies the type of a wake-on-LAN (WOL) packet. |
| [_NDIS_PROCESSOR_VENDOR enumeration](ne-ntddndis-_ndis_processor_vendor.md) | The NDIS_PROCESSOR_VENDOR enumeration identifies a processor vendor. |
| [_NDIS_RECEIVE_FILTER_TEST enumeration](ne-ntddndis-_ndis_receive_filter_test.md) | The NDIS_RECEIVE_FILTER_TEST enumeration identifies the type of test that the receive filter performs. |
| [_NDIS_RECEIVE_FILTER_TYPE enumeration](ne-ntddndis-_ndis_receive_filter_type.md) | The NDIS_RECEIVE_FILTER_TYPE enumeration identifies the receive filter types that the miniport driver supports. |
| [_NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration](ne-ntddndis-_ndis_receive_queue_operational_state.md) | The NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration identifies the current queue state of a receive queue. |
| [_NDIS_RECEIVE_QUEUE_TYPE enumeration](ne-ntddndis-_ndis_receive_queue_type.md) | The NDIS_RECEIVE_QUEUE_TYPE enumeration identifies the type of a receive queue. |
| [_NDIS_REQUEST_TYPE enumeration](ne-ntddndis-_ndis_request_type.md) | The NDIS_REQUEST_TYPE enumeration identifies the request type in an OID request. |
| [_NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration](ne-ntddndis-_ndis_switch_feature_status_type.md) | The NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration specifies the type of status information for a custom policy property, or feature, of a Hyper-V extensible switch. |
| [_NDIS_SWITCH_NIC_STATE enumeration](ne-ntddndis-_ndis_switch_nic_state.md) | The NDIS_SWITCH_NIC_STATE enumeration specifies the current state of the Hyper-V extensible switch network adapter. |
| [_NDIS_SWITCH_NIC_TYPE enumeration](ne-ntddndis-_ndis_switch_nic_type.md) | The NDIS_SWITCH_NIC_TYPE enumeration specifies the type of the virtual network adapter that is attached to a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration](ne-ntddndis-_ndis_switch_port_feature_status_type.md) | The NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration specifies the type of status information for a proprietary policy property, or feature, of a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration](ne-ntddndis-_ndis_switch_port_property_type.md) | The NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch. |
| [_NDIS_SWITCH_PORT_PVLAN_MODE enumeration](ne-ntddndis-_ndis_switch_port_pvlan_mode.md) | The NDIS_SWITCH_PORT_PVLAN_MODE enumeration specifies the operation mode of a private virtual local area network (PVLAN) policy property. This property is specified for a port on the Hyper-V extensible switch. |
| [_NDIS_SWITCH_PORT_STATE enumeration](ne-ntddndis-_ndis_switch_port_state.md) | The NDIS_SWITCH_PORT_STATE enumeration specifies the current state of the Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_TYPE enumeration](ne-ntddndis-_ndis_switch_port_type.md) | The NDIS_SWITCH_PORT_TYPE enumeration specifies the type of a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PORT_VLAN_MODE enumeration](ne-ntddndis-_ndis_switch_port_vlan_mode.md) | The NDIS_SWITCH_PORT_VLAN_MODE enumeration specifies the operation mode of the virtual local area network (VLAN) policy property of a Hyper-V extensible switch port. |
| [_NDIS_SWITCH_PROPERTY_TYPE enumeration](ne-ntddndis-_ndis_switch_property_type.md) | The NDIS_SWITCH_PROPERTY_TYPE enumeration specifies the type of policy property for a Hyper-V extensible switch. |
| [_NDIS_UDP_HEADER_FIELD enumeration](ne-ntddndis-_ndis_udp_header_field.md) | The NDIS_UDP_HEADER_FIELD enumeration identifies the type of a field in a User Datagram Protocol (UDP) header to be filtered. |
