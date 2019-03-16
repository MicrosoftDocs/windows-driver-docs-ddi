---
UID: NS:windot11._DOT11_DISASSOCIATE_PEER_REQUEST
title: _DOT11_DISASSOCIATE_PEER_REQUEST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_disassociate_peer_request.htm
tech.root: netvista
ms.assetid: aa47c030-dcd4-451b-8a4b-03ac566bb394
ms.date: 02/16/2018
ms.keywords: "*PDOT11_DISASSOCIATE_PEER_REQUEST, DOT11_DISASSOCIATE_PEER_REQUEST, DOT11_DISASSOCIATE_PEER_REQUEST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_54282deb-6db8-44b2-b87c-e3f4426141f6.xml, PDOT11_DISASSOCIATE_PEER_REQUEST, PDOT11_DISASSOCIATE_PEER_REQUEST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_DISASSOCIATE_PEER_REQUEST, netvista.dot11_disassociate_peer_request, windot11/DOT11_DISASSOCIATE_PEER_REQUEST, windot11/PDOT11_DISASSOCIATE_PEER_REQUEST"
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   system.
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
- windot11.h
api_name:
- DOT11_DISASSOCIATE_PEER_REQUEST
product:
- Windows
targetos: Windows
req.typenames: DOT11_DISASSOCIATE_PEER_REQUEST, *PDOT11_DISASSOCIATE_PEER_REQUEST
product:
- Windows 10 or later.
---

# _DOT11_DISASSOCIATE_PEER_REQUEST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DISASSOCIATE_PEER_REQUEST structure specifies a disassociation operation in which the NIC
  disassociates from a peer station.


## -syntax


```cpp
typedef struct _DOT11_DISASSOCIATE_PEER_REQUEST {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
  USHORT             usReason;
} DOT11_DISASSOCIATE_PEER_REQUEST, *PDOT11_DISASSOCIATE_PEER_REQUEST;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_DISASSOCIATE_PEER_REQUEST structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_DISASSOCIATE_PEER_REQUEST_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_DISASSOCIATE_PEER_REQUEST).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PeerMacAddr

The media access control (MAC) address of the peer station that the 802.11 station is to
     disassociate from. If
     <b>PeerMacAddr</b> has a value of 0xFF, the 802.11 station must disassociate from all
     associated stations. When
     <b>PeerMacAddr</b> is a unicast address, the 802.11 station must disassociate from a
     specific station.


### -field usReason

A USHORT value that specifies the reason code field in the disassociation frame that is sent by
     the 802.11 miniport driver.


## -remarks



This structure is used with
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-disassociate-peer-request">
    OID_DOT11_DISASSOCIATE_PEER_REQUEST</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-disassociate-peer-request">
   OID_DOT11_DISASSOCIATE_PEER_REQUEST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


