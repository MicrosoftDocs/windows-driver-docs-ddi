---
UID: NS:ntddndis._NDIS_PM_PROTOCOL_OFFLOAD
title: _NDIS_PM_PROTOCOL_OFFLOAD (ntddndis.h)
description: The NDIS_PM_PROTOCOL_OFFLOAD structure specifies parameters for a low power protocol offload to a network adapter.
old-location: netvista\ndis_pm_protocol_offload.htm
tech.root: netvista
ms.assetid: 1ae68e5c-f9ea-4454-b015-82e3af0f7ccd
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PM_PROTOCOL_OFFLOAD, NDIS_PM_PROTOCOL_OFFLOAD, NDIS_PM_PROTOCOL_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_PM_PROTOCOL_OFFLOAD, PNDIS_PM_PROTOCOL_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_PROTOCOL_OFFLOAD, miniport_power_management_ref_f8a5be81-c46e-41cd-ac96-9877e1f9ebec.xml, netvista.ndis_pm_protocol_offload, ntddndis/NDIS_PM_PROTOCOL_OFFLOAD, ntddndis/PNDIS_PM_PROTOCOL_OFFLOAD"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_PM_PROTOCOL_OFFLOAD"
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_PM_PROTOCOL_OFFLOAD
product:
- Windows
targetos: Windows
req.typenames: NDIS_PM_PROTOCOL_OFFLOAD, *PNDIS_PM_PROTOCOL_OFFLOAD
---

# _NDIS_PM_PROTOCOL_OFFLOAD structure


## -description


The <b>NDIS_PM_PROTOCOL_OFFLOAD</b> structure specifies parameters for a low power protocol offload to a
  network adapter.

## -syntax

```C++
typedef struct _NDIS_PM_PROTOCOL_OFFLOAD {
  NDIS_OBJECT_HEADER            Header;
  ULONG                         Flags;
  ULONG                         Priority;
  NDIS_PM_PROTOCOL_OFFLOAD_TYPE ProtocolOffloadType;
  NDIS_PM_COUNTED_STRING        FriendlyName;
  ULONG                         ProtocolOffloadId;
  ULONG                         NextProtocolOffloadOffset;
  union {
    struct {
      ULONG Flags;
      UCHAR RemoteIPv4Address[4];
      UCHAR HostIPv4Address[4];
      UCHAR MacAddress[6];
    } IPv4ARPParameters;
    struct {
      ULONG Flags;
      UCHAR RemoteIPv6Address[16];
      UCHAR SolicitedNodeIPv6Address[16];
      UCHAR MacAddress[6];
      UCHAR TargetIPv6Addresses[2][16];
    } IPv6NSParameters;
    struct {
      ULONG     Flags;
      UCHAR     KCK[DOT11_RSN_KCK_LENGTH];
      UCHAR     KEK[DOT11_RSN_KEK_LENGTH];
      ULONGLONG KeyReplayCounter;
    } Dot11RSNRekeyParameters;
  } ProtocolOffloadParameters;
  _PROTOCOL_OFFLOAD_PARAMETERS  _PROTOCOL_OFFLOAD_PARAMETERS;
} NDIS_PM_PROTOCOL_OFFLOAD, *PNDIS_PM_PROTOCOL_OFFLOAD;
```


## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_PM_PROTOCOL_OFFLOAD). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PM_PROTOCOL_OFFLOAD_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_NDIS_PM_PROTOCOL_OFFLOAD_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field Priority

A ULONG value that contains the priority of the protocol offload. If an overlying driver adds a
     higher priority protocol offload when there are no resources that are available for more protocol offloads, NDIS
     might remove a lower priority protocol offload to free resources. Miniport drivers should ignore this
     member. Protocol drivers can provide any value within the predefined range. The following values are
     predefined:
     





#### NDIS_PM_PROTOCOL_OFFLOAD_PRIORITY_LOWEST

Specifies the lowest priority protocol offload.



#### NDIS_PM_PROTOCOL_OFFLOAD_PRIORITY_NORMAL

Specifies a normal priority protocol offload.



#### NDIS_PM_PROTOCOL_OFFLOAD_PRIORITY_HIGHEST

Specifies the highest priority protocol offload.


### -field ProtocolOffloadType

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_pm_protocol_offload_type">
     NDIS_PM_PROTOCOL_OFFLOAD_TYPE</a> value that contains the type of protocol offload.


### -field FriendlyName

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_counted_string">NDIS_PM_COUNTED_STRING</a> structure
     that contains the user-readable description of the low power protocol offload.


### -field ProtocolOffloadId

A ULONG value that contains an NDIS-provided value that identifies the offloaded protocol. Before
     NDIS sends the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload">OID_PM_ADD_PROTOCOL_OFFLOAD</a> OID
     request down to the underlying NDIS drivers or completes the request to the overlying driver, NDIS sets 
     <b>ProtocolOffloadId</b> to a value that is unique among the protocol offloads on a network adapter.


### -field NextProtocolOffloadOffset

A ULONG value that contains an offset, in bytes. The 
     <b>NextProtocolOffloadOffset</b> member of each <b>NDIS_PM_PROTOCOL_OFFLOAD</b> structure in a list is set to
     the offset (from the beginning of the OID request 
     InformationBuffer) of the next <b>NDIS_PM_PROTOCOL_OFFLOAD</b> structure in the list. If 
     <b>NextProtocolOffloadOffset</b> is zero, the current structure is the last structure in the list.


### -field ProtocolOffloadParameters

A union that contains the following member structures:


### -field ProtocolOffloadParameters.IPv4ARPParameters

A structure that contains IPv4 ARP parameters. This structure contains the following
      members:


### -field ProtocolOffloadParameters.IPv4ARPParameters.Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field ProtocolOffloadParameters.IPv4ARPParameters.RemoteIPv4Address

A <b>UCHAR</b> array that contains an optional IPv4 address. This address represents the Source Protocol
        Address (SPA) field of the ARP request.

If the incoming ARP request has an SPA value that matches this IPv4 address, the network adapter sends an ARP
        response when it is in a low power state. If this member is zero, the network adapter should respond to ARP
        requests from any remote IPv4 address.

For more information about the ARP protocol, see RFC 826.


### -field ProtocolOffloadParameters.IPv4ARPParameters.HostIPv4Address

A <b>UCHAR</b> array that contains the IPv4 address. When it sends the ARP response, the network adapter uses this
       member for the SPA field of the response.


### -field ProtocolOffloadParameters.IPv4ARPParameters.MacAddress

A <b>UCHAR</b> array that contains a media access control (MAC) address. The network adapter uses this MAC address
       for the Source Hardware Address (SHA) field of the ARP response packet that it generates.
       

<div class="alert"><b>Note</b>  When it sends an ARP response, the network adapter must always use this MAC address in the
       ARP payload. However, it should use the current MAC address of the network adapter as the source address in the
       MAC header.</div>
<div> </div>

### -field ProtocolOffloadParameters.IPv6NSParameters

A structure that contains IPv6 Neighbor Solicitation (NS) parameters. This structure contains the
      following members:


### -field ProtocolOffloadParameters.IPv6NSParameters.Flags

A <b>ULONG</b> value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field ProtocolOffloadParameters.IPv6NSParameters.RemoteIPv6Address

A <b>UCHAR</b> array that contains an optional IPv6 address. This address represents the Source Address
        field in the IPv6 header of the NS message.

If the incoming NS message has a Source Address value that matches this IPv6 address, the network adapter
        sends a neighbor advertisement (NA) message when it is in a low power state. If this member is zero,
        the network adapter should respond to NS messages from any remote IPv6 address.

For more information about IPv6 NS and NA messages, see <a href="https://go.microsoft.com/fwlink/p/?linkid=268370">RFC 4861</a>.


### -field ProtocolOffloadParameters.IPv6NSParameters.SolicitedNodeIPv6Address

A <b>UCHAR</b> array that contains the solicited node IPv6 address. For more information about this
       type of IPv6 address, see Multicast IPv6 Addresses.


### -field ProtocolOffloadParameters.IPv6NSParameters.MacAddress

A <b>UCHAR</b> array that contains the MAC address. When it sends the NA message, the network adapter uses this array
        for the target link-layer address (TLLA) field of the NA message.

<div class="alert"><b>Note</b>  When it sends an NA message, the network adapter must always use this MAC address in the
        TLLA field of the NA message. However, it should use the current MAC address of the network adapter as the source
        address in the MAC header.</div>
<div> </div>

### -field ProtocolOffloadParameters.IPv6NSParameters.TargetIPv6Addresses

A <b>UCHAR</b> array that contains one or two IPv6 addresses. If it contains only one address, that address is stored in the first element in the array, and the second element is filled with zeros.

Miniport drivers must consume all addresses in the array.

These addresses represent the Target Address field of an NS message. If one of these addresses
       matches the Target Address field of an incoming NS message, the network adapter sends an NA message in
       response.


### -field ProtocolOffloadParameters.Dot11RSNRekeyParameters

A structure that contains IEEE 802.11i Robust Security Network (RSN) handshake parameters. This
      structure contains the following members:


### -field ProtocolOffloadParameters.Dot11RSNRekeyParameters.Flags

A <b>ULONG</b> value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field ProtocolOffloadParameters.Dot11RSNRekeyParameters.KCK

A <b>UCHAR</b> array that contains an IEEE 802.11 key confirmation key (KCK).


### -field ProtocolOffloadParameters.Dot11RSNRekeyParameters.KEK

A <b>UCHAR</b> array that contains an IEEE 802.11 key encryption key (KEK).


### -field ProtocolOffloadParameters.Dot11RSNRekeyParameters.KeyReplayCounter

A <b>ULONGLONG</b> value that contains a replay counter.


### -field _PROTOCOL_OFFLOAD_PARAMETERS

 




## -remarks



The <b>NDIS_PM_PROTOCOL_OFFLOAD</b> structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload">OID_PM_ADD_PROTOCOL_OFFLOAD</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-protocol-offload-list">
    OID_PM_PROTOCOL_OFFLOAD_LIST</a> OIDs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pm_counted_string">NDIS_PM_COUNTED_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_pm_protocol_offload_type">NDIS_PM_PROTOCOL_OFFLOAD_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-add-protocol-offload">OID_PM_ADD_PROTOCOL_OFFLOAD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pm-protocol-offload-list">OID_PM_PROTOCOL_OFFLOAD_LIST</a>
 

 

