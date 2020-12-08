---
UID: NS:windot11._DOT11_WFD_ATTRIBUTES
title: _DOT11_WFD_ATTRIBUTES (windot11.h)
description: The DOT11_WFD_ATTRIBUTES structure is returned in an NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES indication. The structure defines the attributes related to Wi-Fi Direct (WFD) operation modes.
old-location: netvista\dot11_wfd_attributes.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_ATTRIBUTES structure"]
ms.keywords: "*PDOT11_WFD_ATTRIBUTES, DOT11_WFD_ATTRIBUTES, DOT11_WFD_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_ATTRIBUTES, PDOT11_WFD_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_ATTRIBUTES, netvista.dot11_wfd_attributes, windot11/DOT11_WFD_ATTRIBUTES, windot11/PDOT11_WFD_ATTRIBUTES"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
req.typenames: DOT11_WFD_ATTRIBUTES, *PDOT11_WFD_ATTRIBUTES
f1_keywords:
 - _DOT11_WFD_ATTRIBUTES
 - windot11/_DOT11_WFD_ATTRIBUTES
 - PDOT11_WFD_ATTRIBUTES
 - windot11/PDOT11_WFD_ATTRIBUTES
 - DOT11_WFD_ATTRIBUTES
 - windot11/DOT11_WFD_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - DOT11_WFD_ATTRIBUTES
product:
 - Windows 10 or later.
---

# _DOT11_WFD_ATTRIBUTES structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_ATTRIBUTES</b> structure is returned in an <a href="/previous-versions/windows/hardware/wireless/ff565926(v=vs.85)">NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> indication. The structure defines the  attributes related to Wi-Fi Direct (WFD) operation modes.

## -struct-fields

### -field Header

The type, revision, and size of the <b>DOT11_WFD_ATTRIBUTES</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_ATTRIBUTES_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_ATTRIBUTES_REVISION_1</td>
</tr>
</table>

### -field uNumConcurrentGORole

The number of operational Wi-Fi Direct Group Owner (GO) roles simultaneously supported by the miniport driver. This value is the number of ports that can be simultaneously configured in <b>DOT11_OPERATION_MODE_WFD_GROUP_OWNER</b> operation mode. This member must be less than or equal to  <b>uNumWFDGroup</b> in  <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v3.md">DOT11_VWIFI_COMBINATION_V3</a> returned by the miniport driver.

### -field uNumConcurrentClientRole

The number of operational Wi-Fi Direct Client roles simultaneously supported by the miniport driver. This value is the number of ports that can be simultaneously configured in <b>DOT11_OPERATION_MODE_WFD_CLIENT</b> operation mode. This member must be less than or equal to <b> uNumWFDGroup</b> in  <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v3.md">DOT11_VWIFI_COMBINATION_V3</a> returned by the miniport driver.

### -field WPSVersionsSupported

The Wi-Fi Protected Services (WPS) versions supported by the miniport driver. The miniport driver must be able to interpret WPS Information Elements (IEs) formatted to these supported WPS version specifications.

### -field bServiceDiscoverySupported

If TRUE, the miniport supports sending and responding to WFD Service Discovery Queries. Otherwise, Service Discovery Queries are not supported.

### -field bClientDiscoverabilitySupported

If TRUE, the miniport supports the WFD Client Discoverability. Otherwise, Client Discoverability is not supported.

### -field bInfrastructureManagementSupported

If TRUE, the miniport supports management by the infrastructure network. Otherwise, infrastructure network management is not supported.

### -field uMaxSecondaryDeviceTypeListSize

The maximum number of Secondary Device Types that can be configured on the WFD device.

### -field DeviceAddress

The WFD Peer-to-Peer  (P2P) device address. This address is used as a unique identifier to reference the P2P device.

### -field uInterfaceAddressListCount

The number of P2P Interface Addresses supported by the WFD device. This value must be less than or equal to <b>uNumWFDGroup</b> in <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v3.md">DOT11_VWIFI_COMBINATION_V3</a> returned by the miniport.

### -field pInterfaceAddressList

A pointer to an array of P2P Interface Addresses supported by the WFD device.

### -field uNumSupportedCountryOrRegionStrings

The number of country or region strings supported by the 802.11 station. To support multiple regulatory domains, as specified by the IEEE 802.11d-2001 standard, each country or region string identifies a regulatory domain supported by the 802.11 station.

### -field pSupportedCountryOrRegionStrings

A pointer to an array of 802.11d country or region strings that are supported by the 802.11 station.

### -field uDiscoveryFilterListSize

The maximum number of  Discovery Filters supported by the WFD device for discovery operations. This must be at least 2.

The Discovery filters list that the WFD device must apply for device discovery is specified when <a href="/windows-hardware/drivers/network/oid-dot11-wfd-discover-request">OID_DOT11_WFD_DISCOVER_REQUEST</a> is set.

### -field uGORoleClientTableSize

The maximum number of associations that each WFD GO port supports simultaneously. The miniport must have at least this number of entries in its key-mapping key table.

## -syntax

```cpp
typedef struct _DOT11_WFD_ATTRIBUTES {
  NDIS_OBJECT_HEADER              Header;
  ULONG                           uNumConcurrentGORole;
  ULONG                           uNumConcurrentClientRole;
  ULONG                           WPSVersionsSupported;
  BOOLEAN                         bServiceDiscoverySupported;
  BOOLEAN                         bClientDiscoverabilitySupported;
  BOOLEAN                         bInfrastructureManagementSupported;
  ULONG                           uMaxSecondaryDeviceTypeListSize;
  DOT11_MAC_ADDRESS               DeviceAddress;
  ULONG                           uInterfaceAddressListCount;
  PDOT11_MAC_ADDRESS              pInterfaceAddressList;
  ULONG                           uNumSupportedCountryOrRegionStrings;
  PDOT11_COUNTRY_OR_REGION_STRING pSupportedCountryOrRegionStrings;
  ULONG                           uDiscoveryFilterListSize;
  ULONG                           uGORoleClientTableSize;
} DOT11_WFD_ATTRIBUTES, *PDOT11_WFD_ATTRIBUTES;
```

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-wfd-discover-request">OID_DOT11_WFD_DISCOVER_REQUEST</a>



<a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v3.md">DOT11_VWIFI_COMBINATION_V3</a>



<a href="/previous-versions/windows/hardware/wireless/ff565926(v=vs.85)">NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
