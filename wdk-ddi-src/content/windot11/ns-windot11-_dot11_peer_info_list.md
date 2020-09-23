---
UID: NS:windot11._DOT11_PEER_INFO_LIST
title: _DOT11_PEER_INFO_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_peer_info_list.htm
tech.root: netvista
ms.assetid: 7f75ab1e-8aeb-4e49-9c18-c7a10ce3cbd3
ms.date: 02/16/2018
keywords: ["DOT11_PEER_INFO_LIST structure"]
ms.keywords: "*PDOT11_PEER_INFO_LIST, DOT11_PEER_INFO_LIST, DOT11_PEER_INFO_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_c969625e-444f-4741-a284-6bd77253c8b9.xml, PDOT11_PEER_INFO_LIST, PDOT11_PEER_INFO_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_PEER_INFO_LIST, netvista.dot11_peer_info_list, windot11/DOT11_PEER_INFO_LIST, windot11/PDOT11_PEER_INFO_LIST"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
targetos: Windows
req.typenames: DOT11_PEER_INFO_LIST, *PDOT11_PEER_INFO_LIST
f1_keywords:
 - _DOT11_PEER_INFO_LIST
 - windot11/_DOT11_PEER_INFO_LIST
 - PDOT11_PEER_INFO_LIST
 - windot11/PDOT11_PEER_INFO_LIST
 - DOT11_PEER_INFO_LIST
 - windot11/DOT11_PEER_INFO_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_PEER_INFO_LIST
product:
 - Windows 10 or later.
---

# _DOT11_PEER_INFO_LIST structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>

The DOT11_PEER_INFO_LIST structure specifies a list of <a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a> structures that specify information about all peer stations within an independent basic service set (IBSS) network.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="/windows-hardware/drivers/partnerapps/wi-fi-direct">Wi-Fi Direct</a>.</div>

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_PEER_INFO_LIST structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of <b>Header</b> to the following values:

#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_PEER_INFO_LIST_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_PEER_INFO_LIST).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field uNumOfEntries

The number of entries in the
     <b>PeerInfo</b> array.

### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>PeerInfo</b> array can contain.

### -field PeerInfo

An array that specifies the list of
     <a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a> structures that specify
     information on all peer stations within an IBSS network. Each station is represented by a
     DOT11_PEER_INFO structure.

## -syntax

```cpp
typedef struct _DOT11_PEER_INFO_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  DOT11_PEER_INFO    PeerInfo[1];
} DOT11_PEER_INFO_LIST, *PDOT11_PEER_INFO_LIST;
```

## -remarks

This structure is used with
    <a href="/windows-hardware/drivers/network/oid-dot11-enum-peer-info">OID_DOT11_ENUM_PEER_INFO</a>.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-enum-peer-info">OID_DOT11_ENUM_PEER_INFO</a>



<a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>