---
UID: NS:windot11.DOT11_STATISTICS
title: DOT11_STATISTICS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_statistics.htm
tech.root: netvista
ms.assetid: 714ad442-596b-4e67-82ce-a50e1808a3af
ms.date: 02/16/2018
keywords: ["DOT11_STATISTICS structure"]
ms.keywords: "*PDOT11_STATISTICS, DOT11_STATISTICS, DOT11_STATISTICS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_613cdf17-03f8-47df-963b-f64ce23031e9.xml, PDOT11_STATISTICS, PDOT11_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_statistics, windot11/DOT11_STATISTICS, windot11/PDOT11_STATISTICS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.typenames: DOT11_STATISTICS, *PDOT11_STATISTICS
f1_keywords:
 - DOT11_STATISTICS
 - windot11/DOT11_STATISTICS
 - PDOT11_STATISTICS
 - windot11/PDOT11_STATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_STATISTICS
product:
 - Windows 10 or later.
---

# DOT11_STATISTICS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The DOT11_STATISTICS structure records statistical counters for the 802.11 interface.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_STATISTICS structure. This member is formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_STATISTICS_REVISION_1.



#### Size

This member must be set to `sizeof(DOT11_STATISTICS)`.

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field ullFourWayHandshakeFailures

The number of four-way handshake failures that the 802.11 station encountered during Wi-Fi
     Protected Access (WPA) or Robust Security Network Association (RSNA) authentication.


If the 802.11 station is not performing the WPA or RSNA authentication, it should set this member to
     DOT11_STATISTICS_UNKNOWN.

### -field ullTKIPCounterMeasuresInvoked

The number of times that the 802.11 station invoked countermeasures following a message integrity
     code (MIC) failure.


If the 802.11 station is not performing TKIP countermeasures, it should set this member to
     DOT11_STATISTICS_UNKNOWN.

### -field ullReserved

This member is reserved for use by the operating system. The miniport driver must not write to
     this member.

### -field MacUcastCounters

The MAC layer counters based on unicast packets sent or received by the 802.11 station. The data
     structure for this member is the
     <a href="..\windot11\ns-windot11-dot11_mac_frame_statistics.md">
     DOT11_MAC_FRAME_STATISTICS</a> structure.


<div class="alert"><b>Note</b>  <p class="note"> Counters for received unicast packets must only be incremented for those packets with a
     destination MAC address in the 802.11 MAC header that matches the 802.11 station's MAC
     address.</div>

### -field MacMcastCounters

The MAC layer counters based on multicast or broadcast packets sent or received by the 802.11
     station. The data structure for this member is the
     <a href="..\windot11\ns-windot11-dot11_mac_frame_statistics.md">
     DOT11_MAC_FRAME_STATISTICS</a> structure.


<div class="alert"><b>Note</b>  <p class="note"> Counters for received multicast or broadcast packets must only be incremented for those
     packets with a destination MAC address in the 802.11 MAC header that matches an entry in the multicast
     address list of the 802.11 station. For more information about the multicast address list, see
     <a href="/windows-hardware/drivers/network/oid-dot11-multicast-list">OID_DOT11_MULTICAST_LIST</a>.</div>

### -field PhyCounters

An array of PHY layer counters. Each entry in this array is formatted as a
     <a href="..\windot11\ns-windot11-dot11_phy_frame_statistics.md">
     DOT11_PHY_FRAME_STATISTICS</a> structure.


The miniport driver must maintain an entry within the
     <b>PhyCounters</b> array for each supported PHY. If the 802.11 station supports multiple PHYs of the same
     type, the miniport driver must create separate entries for each.

Entries within the
     <b>PhyCounters</b> array must be in the same order as the list of supported PHYs that the driver returns
     when queried by
     <a href="/windows-hardware/drivers/network/oid-dot11-supported-phy-types">
     OID_DOT11_SUPPORTED_PHY_TYPES</a>.

## -syntax

```cpp
typedef struct DOT11_STATISTICS {
  NDIS_OBJECT_HEADER         Header;
  ULONGLONG                  ullFourWayHandshakeFailures;
  ULONGLONG                  ullTKIPCounterMeasuresInvoked;
  ULONGLONG                  ullReserved;
  DOT11_MAC_FRAME_STATISTICS MacUcastCounters;
  DOT11_MAC_FRAME_STATISTICS MacMcastCounters;
  DOT11_PHY_FRAME_STATISTICS PhyCounters[1];
} DOT11_STATISTICS, *PDOT11_STATISTICS;
```

## -remarks

The miniport driver must unconditionally set all of the counters in the DOT11_STATISTICS structure to
    zero, including MAC-layer and PHY-layer counters, when one of the following occurs:

<ul>
<li>
The driver's
      <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function is
      called.

</li>
<li>
The driver's
      <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function is
      called with an OID set request of <a href="/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>,
      regardless of the type of reset operation specified in the set request.

</li>
</ul>
For more information about the statistics gathered by a Native 802.11 miniport driver, see
    <a href="/windows-hardware/drivers/network/native-802-11-statistics">Native 802.11 Statistics</a>.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-statistics">OID_DOT11_STATISTICS</a>