---
UID: NS:ntddndis._NDIS_OFFLOAD_PARAMETERS
title: _NDIS_OFFLOAD_PARAMETERS (ntddndis.h)
description: The NDIS_OFFLOAD_PARAMETERS structure specifies the current task offload configuration settings in response to an OID set request of OID_TCP_OFFLOAD_PARAMETERS.
old-location: netvista\ndis_offload_parameters.htm
tech.root: netvista
ms.date: 01/30/2024
ms.keywords: "*PNDIS_OFFLOAD_PARAMETERS, NDIS_ENCAPSULATION_TYPE_GRE_MAC, NDIS_OFFLOAD_PARAMETERS, NDIS_OFFLOAD_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_AND_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_ENABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV1_DISABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV1_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED, NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED, NDIS_OFFLOAD_PARAMETERS_LSOV1_DISABLED, NDIS_OFFLOAD_PARAMETERS_LSOV1_ENABLED, NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED, NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED, NDIS_OFFLOAD_PARAMETERS_NO_CHANGE, NDIS_OFFLOAD_PARAMETERS_REVISION_1, NDIS_OFFLOAD_PARAMETERS_REVISION_2, NDIS_OFFLOAD_PARAMETERS_REVISION_3, NDIS_OFFLOAD_PARAMETERS_RSC_DISABLED, NDIS_OFFLOAD_PARAMETERS_RSC_ENABLED, NDIS_OFFLOAD_SET_NO_CHANGE, NDIS_OFFLOAD_SET_OFF, NDIS_OFFLOAD_SET_ON, PNDIS_OFFLOAD_PARAMETERS, PNDIS_OFFLOAD_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OFFLOAD_PARAMETERS, netvista.ndis_offload_parameters, ntddndis/NDIS_OFFLOAD_PARAMETERS, ntddndis/PNDIS_OFFLOAD_PARAMETERS, tcpip_offload_ref_9ae50974-12a7-4c63-973e-27684a4f1474.xml"
req.header: ntddndis.h
req.construct-type: structure
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista,Supported in NDIS 6.0 and later.
req.target-min-winversvr: Windows Server 2008
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
req.typenames: NDIS_OFFLOAD_PARAMETERS, *PNDIS_OFFLOAD_PARAMETERS
f1_keywords:
 - _NDIS_OFFLOAD_PARAMETERS
 - ntddndis/_NDIS_OFFLOAD_PARAMETERS
 - PNDIS_OFFLOAD_PARAMETERS
 - ntddndis/PNDIS_OFFLOAD_PARAMETERS
 - NDIS_OFFLOAD_PARAMETERS
 - ntddndis/NDIS_OFFLOAD_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_OFFLOAD_PARAMETERS
 - PNDIS_OFFLOAD_PARAMETERS
 - NDIS_OFFLOAD_PARAMETERS
---

# NDIS_OFFLOAD_PARAMETERS structure (ntddndis.h)




## -description

The **NDIS_OFFLOAD_PARAMETERS** structure specifies the current task offload configuration settings in
  response to an 
  OID set request of [OID_TCP_OFFLOAD_PARAMETERS](/windows-hardware/drivers/network/oid-tcp-offload-parameters).

## -struct-fields

### -field Header

The [**NDIS_OBJECT_HEADER**](/windows-hardware/drivers/ddi/content/objectheader/ns-objectheader-ndis_object_header) structure for the **NDIS_OFFLOAD_PARAMETERS** structure. Set the **Type** member of the structure that **Header** specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the **NDIS_OFFLOAD_PARAMETERS** structure, set the **Revision** member to one of the following values:

| Value                              | Meaning   |
|------------------------------------|-----------|
| **NDIS_OFFLOAD_PARAMETERS_REVISION_6**<br>6 | Supports the **UdpRsc** member for NDIS 6.89. Set the **Size** member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_6. |
| **NDIS_OFFLOAD_PARAMETERS_REVISION_5**<br>5 | Supports the **UdpSegmentation** for IPv4 and IPv6 for NDIS 6.83. Set the **Size** member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_5. |
| **NDIS_OFFLOAD_PARAMETERS_REVISION_4**<br>4 | Supports the **EncapsulationProtocolParameters** and its nested **VxlanParameters** for NDIS 6.50. Set the **Size** member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_4. |
| **NDIS_OFFLOAD_PARAMETERS_REVISION_3**<br>3 | Supports the **RscIPv4**, **RscIPv6**, **EncapsulatedPacketTaskOffload**, and **EncapsulationTypes** members for NDIS 6.30. Set the **Size** member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_3. |
| **NDIS_OFFLOAD_PARAMETERS_REVISION_2**<br>2 | Supports the **IPsecV2**, **IPsecV2IPv4**, **Reserved1**, and **Reserved2** members for NDIS 6.1. Set the **Size** member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_2. |
| **NDIS_OFFLOAD_PARAMETERS_REVISION_1**<br>1 | Original version for NDIS 6.0. Set the **Size** member to NDIS_SIZEOF_OFFLOAD_PARAMETERS_REVISION_1. |


### -field IPv4Checksum

The IPv4 checksum setting of the miniport adapter. For more information, see the following Remarks
     section.

### -field TCPIPv4Checksum

The IPv4 checksum setting of the miniport adapter for TCP packets. For more information, see the
     following Remarks section.

### -field UDPIPv4Checksum

The IPv4 checksum setting of the miniport adapter for UDP packets. For more information, see the
     following Remarks section.

### -field TCPIPv6Checksum

The IPv6 checksum setting of the miniport adapter for TCP packets. For more information, see the
     following Remarks section.

### -field UDPIPv6Checksum

The IPv6 checksum setting of the miniport adapter for UDP packets. For more information, see the
     following Remarks section.

### -field LsoV1

The large send offload version 1 (LSOV1) setting of the miniport adapter. This setting should be one of the following values:

| Value                                   | Meaning                                     |
|-----------------------------------------|---------------------------------------------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**   | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_LSOV1_DISABLED** | LSOV1 is disabled.                         |
| **NDIS_OFFLOAD_PARAMETERS_LSOV1_ENABLED**  | LSOV1 is enabled.                          |


### -field IPsecV1

The Internet protocol security (IPsec) offload setting of the miniport adapter. This setting
     should be one of the following values:

| Value                                       | Meaning |
|---------------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**       | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV1_DISABLED**| IPsec offload is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_ENABLED** | The IPsec offload Authentication Header (AH) feature should be enabled for transmit and receive. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV1_ESP_ENABLED** | The IPsec offload Encapsulating Security Payload (ESP) feature should be enabled for transmit and receive. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV1_AH_AND_ESP_ENABLED** | The IPsec offload AH and ESP features are enabled for transmit and receive. |

### -field LsoV2IPv4

The IPv4 large send offload version 2 (LSOV2) setting of the miniport adapter. This setting should be one of the following values:

| Value                                   | Meaning |
|-----------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**   | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED** | LSOV2 for IPv4 is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED**  | LSOV2 for IPv4 is enabled. |


### -field LsoV2IPv6

The IPv6 LSOV2 setting of the miniport adapter. These settings are specified as one of the
     following values:

| Value                                   | Meaning |
|-----------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**   | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_LSOV2_DISABLED** | LSOV2 for IPv6 is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_LSOV2_ENABLED**  | LSOV2 for IPv6 is enabled. |


### -field TcpConnectionIPv4

The IPv4 connection offload setting of the miniport adapter. These settings are specified as one
     of the following values:

| Value                                   | Meaning |
|-----------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**   | The miniport driver should not change the current setting. |


### -field TcpConnectionIPv6

The IPv6 connection offload setting of the miniport adapter. These settings are specified as one of the following values:
     
| Value                                   | Meaning |
|-----------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**   | The miniport driver should not change the current setting. |


### -field Flags

A set of flags that can be combined with a bitwise OR operation. Set this member to zero or the following value:

| Value                                   | Meaning |
|-----------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_SKIP_REGISTRY_UPDATE**<br>0x00000001   | Allows UDP Receive Segment Coalescing Offload (URO) to be disabled only at runtime. Changes made with this flag aren't saved to the registry. |

### -field IPsecV2

The Internet protocol security (IPsec) offload version 2 setting of a miniport adapter that supports IPv6 and IPv4. This member specifies the setting for both IPv6 and IPv4 support. This setting should be one of the following values:

| Value                                             | Meaning |
|---------------------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**             | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED**      | IPsec offload version 2 is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED**    | The IPsec offload version 2 Authentication Header (AH) feature should be enabled for transmit and receive. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED**   | The IPsec offload version 2 Encapsulating Security Payload (ESP) feature should be enabled for transmit and receive. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED** | The IPsec offload version 2 AH and ESP features are enabled for transmit and receive. |


### -field IPsecV2IPv4

The Internet protocol security (IPsec) offload version 2 setting of a miniport adapter that supports
      IPv4 and does not support IPv6. If the miniport driver supports IPv6, the 
      <b>IPsecV2</b> member specifies the IPv4 setting and this member is not used. This setting should be one
      of the following values:

| Value                                             | Meaning |
|---------------------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**             | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_DISABLED**      | IPsec offload version 2 is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_ENABLED**    | The IPsec offload version 2 Authentication Header (AH) feature should be enabled for transmit and receive. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_ESP_ENABLED**   | The IPsec offload version 2 Encapsulating Security Payload (ESP) feature should be enabled for transmit and receive. |
| **NDIS_OFFLOAD_PARAMETERS_IPSECV2_AH_AND_ESP_ENABLED** | The IPsec offload version 2 AH and ESP features are enabled for transmit and receive. |


### -field RscIPv4

Indicates Receive Segment Coalescing state for IPv4.

| Value                                           | Meaning                |
|-------------------------------------------------|------------------------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**           | The RSC state is unchanged. |
| **NDIS_OFFLOAD_PARAMETERS_RSC_ENABLED**         | The RSC state is enabled.   |
| **NDIS_OFFLOAD_PARAMETERS_RSC_DISABLED**        | The RSC state is disabled.  |

### -field RscIPv6

Indicates Receive Segment Coalescing state for IPv6.

| Value                                           | Meaning                |
|-------------------------------------------------|------------------------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**           | The RSC state is unchanged. |
| **NDIS_OFFLOAD_PARAMETERS_RSC_ENABLED**         | The RSC state is enabled.   |
| **NDIS_OFFLOAD_PARAMETERS_RSC_DISABLED**        | The RSC state is disabled.  |


### -field EncapsulatedPacketTaskOffload

A protocol driver sets **EncapsulatedPacketTaskOffload** as follows: 

**Note**: For receive side offloads such as VMQ and RSS, there are other set OIDs that the protocol driver sends down to enable and configure the offload parameters (for example, queues, hash, and indirection table). The **EncapsulatedPacketTaskOffload** member is supplemental to those OIDs and instructs the NIC to also do these offloads for encapsulated packets.

| Value                         | Meaning |
|-------------------------------|---------|
| **NDIS_OFFLOAD_SET_NO_CHANGE**<br>0| The NVGRE and VXLAN task offload states are unchanged. |
| **NDIS_OFFLOAD_SET_ON**<br>1      | Enables NVGRE and VXLAN task offloads. |
| **NDIS_OFFLOAD_SET_OFF**<br>2     | Disables NVGRE and VXLAN task offloads. |

### -field EncapsulationTypes

This field is effective only when the <b>EncapsulatedPacketTaskOffload</b> is set to <b>NDIS_OFFLOAD_SET_ON</b>. If the <b>EncapsulatedPacketTaskOffload</b> member is not set to <b>NDIS_OFFLOAD_SET_ON</b>, this member is zero. A protocol driver must set <b>EncapsulationTypes</b> to the bitwise OR of the flags corresponding to encapsulation types that it requires. It can select flags from the following:

| Value                                  | Meaning                          |
|----------------------------------------|----------------------------------|
| **NDIS_ENCAPSULATION_TYPE_GRE_MAC**<br>0x00000001 | Specifies GRE MAC encapsulation (NVGRE). |
| **NDIS_ENCAPSULATION_TYPE_VXLAN**<br>0x00000002   | Specifies VXLAN encapsulation.           |


### -field EncapsulationProtocolParameters

A union that describes the encapsulation parameters for VXLAN encapsulation. 

If the miniport driver advertised **VxlanUDPPortNumerConfigurable** as **TRUE**, then a protocol driver can set **EncapsulationProtocolParameters.VxlanParameters.VxlanUDPPortNumber** to a non-0 value. The miniport driver must use this port number for matching and generating VXLAN frames after succeeding the OID, and also advertise the updated value in its capabilities. If the protocol driver passes a value of **0**, then the miniport driver continues to use the port number initialized from the standardized keyword.

### -field EncapsulationProtocolParameters.VxlanParameters

A structure that contains the **VxlanUDPPortNumber**.

### -field EncapsulationProtocolParameters.VxlanParameters.VxlanUDPPortNumber

The VXLAN destination port value. This value is set to the IANA-assigned value of 4789 by default. If the miniport driver supports a configurable port number as advertised in the [**NDIS_OFFLOAD**](../ntddndis/ns-ntddndis-_ndis_offload.md) structure, a protocol driver can issue an [OID_TCP_OFFLOAD_PARAMETERS](/windows-hardware/drivers/network/oid-tcp-offload-parameters) OID to enable NDIS_ENCAPSULATION_TYPE_VXLAN with a different value in **VxlanUDPPortNumber**. The miniport driver must use **VxlanUDPPortNumber** to determine VXLAN encapsulated packets for performing receive offloads.

### -field EncapsulationProtocolParameters.Value

The port value if **EncapsulationTypes** is not set to NDIS_ENCAPSULATION_TYPE_VXLAN.

### -field _ENCAPSULATION_PROTOCOL_PARAMETERS

The type name for **EncapsulationProtocolParameters**.

### -field UdpSegmentation

A structure that describes the miniport adapter's UDP Segmentation Offload (USO) settings.

### -field UdpSegmentation.IPv4

The IPv4 UDP Segmentation Offload (USO) setting of the miniport adapter. This setting should be one of the following values:     

| Value                                        | Meaning |
|----------------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**        | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_UDP_SEG_DISABLED** | USO is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_UDP_SEG_ENABLED**  | USO is enabled. |


### -field UdpSegmentation.IPv6

The IPv6 UDP Segmentation Offload (USO) setting of the miniport adapter. This setting should be one of the following values:     

| Value                                        | Meaning |
|----------------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_NO_CHANGE**        | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_UDP_SEG_DISABLED** | USO is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_UDP_SEG_ENABLED**  | USO is enabled. |

### -field UdpRsc

A structure that describes the miniport adapter's UDP Receive Segment Coalescing Offload (URO) settings.

### -field UdpRsc.Enabled

The URO setting of the miniport adapter. This setting should be one of the following values:

| Value                                        | Meaning |
|----------------------------------------------|---------|
| **NDIS_OFFLOAD_PARAMETERS_UDP_RSC_NO_CHANGE**<br>0 | The miniport driver should not change the current setting. |
| **NDIS_OFFLOAD_PARAMETERS_UDP_RSC_DISABLED**<br>1 | URO is disabled. |
| **NDIS_OFFLOAD_PARAMETERS_UDP_RSC_ENABLED**<br>2  | URO is enabled. |

## -remarks

In response to an [OID_TCP_OFFLOAD_PARAMETERS](/windows-hardware/drivers/network/oid-tcp-offload-parameters) OID set request, a miniport driver uses the settings in the **NDIS_OFFLOAD_PARAMETERS** structure to set the current configuration of the miniport adapter.

NDIS retains the requested settings in the registry in the offload standardized keywords. When NDIS restarts the miniport adapter, the miniport driver reads the offload standardized keywords and uses them to set the default offload configuration of the NIC.

To access the checksum offload settings, use the following members of the **NDIS_OFFLOAD_PARAMETERS** structure:

**IPv4Checksum**

**TCPIPv4Checksum**

**UDPIPv4Checksum**

**TCPIPv6Checksum**

**UDPIPv6Checksum**


The preceding members can have one of the following values:

NDIS_OFFLOAD_PARAMETERS_NO_CHANGE  
The miniport driver should not change the current setting.

NDIS_OFFLOAD_PARAMETERS_TX_RX_DISABLED  
The feature that the member specifies is disabled.

NDIS_OFFLOAD_PARAMETERS_TX_ENABLED_RX_DISABLED  
The feature that the member specifies is enabled for transmit and disabled for receive.

NDIS_OFFLOAD_PARAMETERS_RX_ENABLED_TX_DISABLED  
The feature that the member specifies is enabled for receive and disabled for transmit.

NDIS_OFFLOAD_PARAMETERS_TX_RX_ENABLED  
The feature that the member specifies is enabled for transmit and receive.

## -see-also

[NDIS_OBJECT_HEADER](/windows-hardware/drivers/ddi/content/objectheader/ns-objectheader-ndis_object_header)

[OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities)

[OID_TCP_OFFLOAD_PARAMETERS](/windows-hardware/drivers/network/oid-tcp-offload-parameters)


