---
UID: NS:windot11._DOT11_WFD_DEVICE_ENTRY
title: _DOT11_WFD_DEVICE_ENTRY (windot11.h)
description: The DOT11_WFD_DEVICE_ENTRY structure contains information about a discovered Wi-Fi Direct (WFD) device, a discovered WFD Group Owner (GO), or a discovered infrastructure access point.
old-location: netvista\_dot11_wfd_device_entry.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_DEVICE_ENTRY structure"]
ms.keywords: "*PDOT11_WFD_DEVICE_ENTRY, DOT11_WFD_DEVICE_ENTRY, DOT11_WFD_DEVICE_ENTRY structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DEVICE_ENTRY, PDOT11_WFD_DEVICE_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DEVICE_ENTRY, netvista._dot11_wfd_device_entry, windot11/ DOT11_WFD_DEVICE_ENTRY, windot11/PDOT11_WFD_DEVICE_ENTRY"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
req.typenames: DOT11_WFD_DEVICE_ENTRY, *PDOT11_WFD_DEVICE_ENTRY
f1_keywords:
 - _DOT11_WFD_DEVICE_ENTRY
 - windot11/_DOT11_WFD_DEVICE_ENTRY
 - PDOT11_WFD_DEVICE_ENTRY
 - windot11/PDOT11_WFD_DEVICE_ENTRY
 - DOT11_WFD_DEVICE_ENTRY
 - windot11/DOT11_WFD_DEVICE_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_DEVICE_ENTRY
 - PDOT11_WFD_DEVICE_ENTRY
 - DOT11_WFD_DEVICE_ENTRY
---

# _DOT11_WFD_DEVICE_ENTRY structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The <b>DOT11_WFD_DEVICE_ENTRY</b> structure contains information about a discovered Wi-Fi Direct (WFD) device, a discovered WFD Group Owner (GO), or a discovered infrastructure access point. This structure is returned from both an <a href="/windows-hardware/drivers/network/oid-dot11-wfd-enum-device-list">OID_DOT11_WFD_ENUM_DEVICE_LIST</a> and a <a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-discover-complete">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a> notification.

## -struct-fields

### -field uPhyId

The identifier of the PHY the miniport used to detect the device. This identifier is in the index range of the list of supported PHYs returned from an <a href="/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a> query request. This identifier cannot be <b>DOT_PHY_ID_ANY</b>.

### -field PhySpecificInfo

The attributes of the PHY identified by <b>uPhyId</b>.

### -field dot11BSSID

The MAC address of the device that sent the beacon or probe response packet during a discovery.

### -field dot11BSSType

The BSS network type. This member is set to <b>dot11_BSS_type_infrastructure</b> for all discovered WFD devices and WFD GOs.

### -field TransmitterAddress

The MAC address for the transmitter of the device that sent the beacon or probe response packet during a discovery.

### -field lRSSI

The received signal strength indicator value of the discovered device. The units for this value are in decibels referenced to 1 milliwatt (dBm).

### -field uLinkQuality

Link quality value ranging from 0 to 100. A value of 100 indicates highest link quality.

### -field usBeaconPeriod

The value received from the beacon interval field of the most recent beacon or probe response packet.

### -field ullTimestamp

The value received from the timestamp field of the most recent beacon or probe response packet.

### -field ullBeaconHostTimestamp

The timestamp, determined by a value returned from <a href="..\ndis\nf-ndis-ndisgetcurrentsystemtime.md">NdisGetCurrentSystemTime</a>, recording the time when the beacon packet was received.

### -field ullProbeResponseHostTimestamp

The timestamp, determined by a value returned from <a href="..\ndis\nf-ndis-ndisgetcurrentsystemtime.md">NdisGetCurrentSystemTime</a>, recording the time when the probe response packet was received.

### -field usCapabilityInformation

The value received from the capability field of the most recent beacon or probe response packet.

### -field uBeaconIEsOffset

The offset, in bytes, from the beginning of this structure  of the list of information elements (IEs) from the last beacon packet received from this device. If no beacon packet was received, this value should be 0.

### -field uBeaconIEsLength

The length, in bytes, of the IEs at <b>uBeaconIEsOffset</b>. This is an exact length value and contains no padding for alignment. If no beacon packet was received, this value should be 0.

### -field uProbeResponseIEsOffset

The offset, in bytes, from the beginning of this structure  of the list of information elements (IEs) from the last probe response packet received from this device. If no beacon packet was received, this value should be 0.

### -field uProbeResponseIEsLength

The length, in bytes, of the IEs at <b>uProbeResponseIEsOffset</b>. This is an exact length value and contains no padding for alignment. If no probe response packet was received, this value should be 0.

## -syntax

```cpp
typedef struct _DOT11_WFD_DEVICE_ENTRY {
  ULONG                             uPhyId;
  DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO PhySpecificInfo;
  DOT11_MAC_ADDRESS                 dot11BSSID;
  DOT11_BSS_TYPE                    dot11BSSType;
  DOT11_MAC_ADDRESS                 TransmitterAddress;
  LONG                              lRSSI;
  ULONG                             uLinkQuality;
  USHORT                            usBeaconPeriod;
  ULONGLONG                         ullTimestamp;
  ULONGLONG                         ullBeaconHostTimestamp;
  ULONGLONG                         ullProbeResponseHostTimestamp;
  USHORT                            usCapabilityInformation;
  ULONG                             uBeaconIEsOffset;
  ULONG                             uBeaconIEsLength;
  ULONG                             uProbeResponseIEsOffset;
  ULONG                             uProbeResponseIEsLength;
}  DOT11_WFD_DEVICE_ENTRY, *PDOT11_WFD_DEVICE_ENTRY;
```

## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>



<a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-discover-complete">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a>



<a href="/windows-hardware/drivers/network/oid-dot11-wfd-enum-device-list">OID_DOT11_WFD_ENUM_DEVICE_LIST</a>



<a href="/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



<a href="..\windot11\ns-windot11-dot11_bss_entry_phy_specific_info.md">DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO</a>



<a href="..\ndis\nf-ndis-ndisgetcurrentsystemtime.md">NdisGetCurrentSystemTime</a>

