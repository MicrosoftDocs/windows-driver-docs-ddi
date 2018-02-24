---
UID: NS:ndis._NET_IF_INFORMATION
title: "_NET_IF_INFORMATION"
author: windows-driver-content
description: The NET_IF_INFORMATION structure provides NDIS with information about a registered network interface.
old-location: netvista\net_if_information.htm
old-project: netvista
ms.assetid: 5508650c-473c-4710-869e-053481e83f1b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNET_IF_INFORMATION, net_if_struct_ref_ceb46daa-0e14-4ed8-9f05-9cd064a57dfb.xml, ndis/NET_IF_INFORMATION, NET_IF_INFORMATION structure [Network Drivers Starting with Windows Vista], NET_IF_INFORMATION, PNET_IF_INFORMATION structure pointer [Network Drivers Starting with Windows Vista], ndis/PNET_IF_INFORMATION, _NET_IF_INFORMATION, netvista.net_if_information, PNET_IF_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NET_IF_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PNET_IF_INFORMATION, NET_IF_INFORMATION"
---

# _NET_IF_INFORMATION structure


## -description


The NET_IF_INFORMATION structure provides NDIS with information about a registered network
  interface.


## -syntax


````
typedef struct _NET_IF_INFORMATION {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  Flags;
  NET_PHYSICAL_LOCATION  PhysicalLocation;
  ULONG                  WanTunnelType;
  ULONG                  PortNumber;
  NET_IF_ACCESS_TYPE     AccessType;
  NET_IF_DIRECTION_TYPE  DirectionType;
  NET_IF_CONNECTION_TYPE ConnectionType;
  BOOLEAN                ifConnectorPresent;
  USHORT                 PhysAddressLength;
  USHORT                 PhysAddressOffset;
  USHORT                 PermanentPhysAddressOffset;
  USHORT                 FriendlyNameLength;
  USHORT                 FriendlyNameOffset;
  GUID                   InterfaceGuid;
  NET_IF_NETWORK_GUID    NetworkGuid;
  ULONG                  SupportedStatistics;
  NDIS_MEDIUM            MediaType;
  NDIS_PHYSICAL_MEDIUM   PhysicalMediumType;
} NET_IF_INFORMATION, *PNET_IF_INFORMATION;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     interface information structure (NET_IF_INFORMATION). The provider sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_NET_IF_INFORMATION_REVISION_1.


### -field Flags

Flags that provide information about the interface that this structure describes. These flags are
     combined with a bitwise OR operation. If none of the flags applies, set this member to zero. The
     following flag values are defined:
     





#### NIIF_HARDWARE_INTERFACE

Set if the network interface is for hardware.



#### NIIF_FILTER_INTERFACE

Set if the network interface is for a filter module.



#### NIIF_NDIS_RESERVED1

Reserved for NDIS.



#### NIIF_NDIS_RESERVED2

Reserved for NDIS.



#### NIIF_NDIS_RESERVED3

Reserved for NDIS.


### -field PhysicalLocation

The physical location for the hardware that is associated with an interface specified in a 
     <a href="https://msdn.microsoft.com/e5661e05-a83f-4632-af98-2a021eeb7d80">
     NET_PHYSICAL_LOCATION</a> structure.


### -field WanTunnelType

The tunnelIfEncapsMethod (from 
     RFC 2667) for WAN devices. If the WAN tunnel type is unknown, set this
     member to NIIF_WAN_TUNNEL_TYPE_UNKNOWN.


### -field PortNumber

The NDIS port number for the interface.


### -field AccessType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.


### -field DirectionType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a> NDIS network
     interface direction type.


### -field ConnectionType

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a> NDIS network
     interface connection type.


### -field ifConnectorPresent

A Boolean value that indicates if a connector is present. Set this value to <b>TRUE</b> if there is a
     physical adapter or <b>FALSE</b> if there is no physical adapter.


### -field PhysAddressLength

The length, in bytes, of the physical address or MAC address. This length is the length of the
     byte arrays that are located at the offsets that the 
     <b>PhysAddressOffset</b> and 
     <b>PermanentPhysAddressOffset</b> members specify.


### -field PhysAddressOffset

The offset of the current physical address, in bytes, from the beginning of this structure. The
     current physical address is an array of bytes. The length of the array is specified in the 
     <b>PhysAddressLength</b> member. The current physical address is the same value that the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a> OID
     returns.


### -field PermanentPhysAddressOffset

The offset of the permanent physical address, in bytes, from the beginning of this structure. The
     permanent physical address is an array of bytes. The length of the array is specified in the 
     <b>PhysAddressLength</b> member. The permanent physical address is the same value that the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569074">OID_802_3_PERMANENT_ADDRESS</a> OID
     returns.


### -field FriendlyNameLength

The length, in bytes, of the friendly name for the interface that this structure describes. This
     length is the length of the WCHAR array that is located at the offset in the 
     <b>FriendlyNameOffset</b> member.


### -field FriendlyNameOffset

The offset of the beginning of the friendly name, in bytes, from the beginning of this structure.
     This name should include the name of the manufacturer, the product, and the version of the interface
     hardware and software. The name is specified as an array of WCHAR values. The 
     <b>FriendlyNameLength</b> member specifies the length of the array.


### -field InterfaceGuid

The GUID that is associated with the interface. The interface provider generates the interface
     GUID for the interface. The provider can call the 
     <a href="..\ntddk\nf-ntddk-exuuidcreate.md">ExUuidCreate</a> routine to create the GUID. The
     interface GUID should be associated with the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value that is assigned to the interface.
     If the provider retains information about the interface in persistent storage, it should save the GUID
     and reuse the GUID when it reregisters the interface after the computer restarts.


### -field NetworkGuid

The GUID that is associated with the network that the interface belongs to. If the interface
     provider cannot provide the network GUID, it can pass a zero GUID. In this case, NDIS will register the
     interface in the default network of the primary compartment.


### -field SupportedStatistics

The statistics that the interface supports. For more information, see the 
     <b>SupportedStatistics</b> member of the 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure .


### -field MediaType

The 
     <b>NdisMedium</b><i>Xxx</i> type that the interface supports. For more information, see 
     <a href="..\ntddndis\ne-ntddndis-_ndis_medium.md">NDIS_MEDIUM</a>.


### -field PhysicalMediumType

The physical medium type for the interface. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>



## -remarks



A network interface provider initializes a NET_IF_INFORMATION structure to provide NDIS with
    information about a registered interface. To register an interface, a provider passes a pointer to a
    NET_IF_INFORMATION structure to the 
    <a href="..\ndis\nf-ndis-ndisifregisterinterface.md">
    NdisIfRegisterInterface</a> function.

The interface provider should allocate enough memory for the structure and the arrays that the 
    <b>PhysAddressOffset</b>, 
    <b>PermanentPhysAddressOffset</b>, and 
    <b>FriendlyNameOffset</b> members specify. The provider must provide the values for the arrays after the
    structure and set the offset members to identify the location of the arrays.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569074">OID_802_3_PERMANENT_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568750">NET_PHYSICAL_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>



<a href="..\ndis\nf-ndis-ndisifregisterinterface.md">NdisIfRegisterInterface</a>



<a href="..\ntddk\nf-ntddk-exuuidcreate.md">ExUuidCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568750">NET_PHYSICAL_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_medium.md">NDIS_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_IF_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

