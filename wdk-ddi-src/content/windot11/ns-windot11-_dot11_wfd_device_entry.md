---
UID: NS:windot11._DOT11_WFD_DEVICE_ENTRY
title: _DOT11_WFD_DEVICE_ENTRY (windot11.h)
description: The DOT11_WFD_DEVICE_ENTRY structure contains information about a discovered Wi-Fi Direct (WFD) device, a discovered WFD Group Owner (GO), or a discovered infrastructure access point.
old-location: netvista\_dot11_wfd_device_entry.htm
tech.root: netvista
ms.assetid: 548A40F7-1C02-4BF0-8F78-EB8C3C97CEB4
ms.date: 02/16/2018
ms.keywords: "*PDOT11_WFD_DEVICE_ENTRY, DOT11_WFD_DEVICE_ENTRY, DOT11_WFD_DEVICE_ENTRY structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DEVICE_ENTRY, PDOT11_WFD_DEVICE_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DEVICE_ENTRY, netvista._dot11_wfd_device_entry, windot11/ DOT11_WFD_DEVICE_ENTRY, windot11/PDOT11_WFD_DEVICE_ENTRY"
f1_keywords:
 - "windot11/DOT11_WFD_DEVICE_ENTRY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Windot11.h
api_name:
- DOT11_WFD_DEVICE_ENTRY
targetos: Windows
req.typenames: DOT11_WFD_DEVICE_ENTRY, *PDOT11_WFD_DEVICE_ENTRY
product:
- Windows 10 or later.
---

# _DOT11_WFD_DEVICE_ENTRY structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_DEVICE_ENTRY</b> structure contains information about a discovered Wi-Fi Direct (WFD) device, a discovered WFD Group Owner (GO), or a discovered infrastructure access point. This structure is returned from both an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-enum-device-list">OID_DOT11_WFD_ENUM_DEVICE_LIST</a> and a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-discover-complete">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a> notification.


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


## -struct-fields




### -field uPhyId

The identifer of the PHY the miniport used to detect the device. This identifier is in the index range of the list of supported PHYs returned from an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a> query request. This identifer cannot be <b>DOT_PHY_ID_ANY</b>.


### -field PhySpecificInfo

The attributes of the PHY identified by <b>uPhyId</b>.


### -field dot11BSSID

The MAC address of the device that sent the beacon or probe response packet during a discovery.


### -field dot11BSSType

The BSS network type. This member is set to <b>dot11_BSS_type_infrastructure</b> for all discovered WFD devices and WFD GOs.


### -field TransmitterAddress

The MAC address for the transmitter of the device that sent the beacon or probe response packet during a discovery.


### -field lRSSI

The recieved signal strength indicator value of the discovered device. The units for this value are in decibels referenced to 1 milliwatt (dBm).


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


## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-discover-complete">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-enum-device-list">OID_DOT11_WFD_ENUM_DEVICE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



<a href="..\windot11\ns-windot11-dot11_bss_entry_phy_specific_info.md">DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO</a>



<a href="..\ndis\nf-ndis-ndisgetcurrentsystemtime.md">NdisGetCurrentSystemTime</a>



 

 


