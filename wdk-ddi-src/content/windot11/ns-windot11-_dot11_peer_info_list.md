---
UID: NS:windot11._DOT11_PEER_INFO_LIST
title: _DOT11_PEER_INFO_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_peer_info_list.htm
tech.root: netvista
ms.assetid: 7f75ab1e-8aeb-4e49-9c18-c7a10ce3cbd3
ms.date: 02/16/2018
ms.keywords: "*PDOT11_PEER_INFO_LIST, DOT11_PEER_INFO_LIST, DOT11_PEER_INFO_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_c969625e-444f-4741-a284-6bd77253c8b9.xml, PDOT11_PEER_INFO_LIST, PDOT11_PEER_INFO_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_PEER_INFO_LIST, netvista.dot11_peer_info_list, windot11/DOT11_PEER_INFO_LIST, windot11/PDOT11_PEER_INFO_LIST"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	windot11.h
api_name:
-	DOT11_PEER_INFO_LIST
product:
- Windows
targetos: Windows
req.typenames: DOT11_PEER_INFO_LIST, *PDOT11_PEER_INFO_LIST
product:
- Windows 10 or later.
---

# _DOT11_PEER_INFO_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>

The DOT11_PEER_INFO_LIST structure specifies a list of <a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a> structures that specify information about all peer stations within an independent basic service set (IBSS) network.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="https://msdn.microsoft.com/library/windows/hardware/mt244265">Wi-Fi Direct</a>.</div>

## -syntax


```cpp
typedef struct _DOT11_PEER_INFO_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  DOT11_PEER_INFO    PeerInfo[1];
} DOT11_PEER_INFO_LIST, *PDOT11_PEER_INFO_LIST;
```


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


## -remarks



This structure is used with
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569361">OID_DOT11_ENUM_PEER_INFO</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569361">OID_DOT11_ENUM_PEER_INFO</a>



<a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


