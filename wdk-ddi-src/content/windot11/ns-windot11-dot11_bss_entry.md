---
UID: NS:windot11.DOT11_BSS_ENTRY
title: DOT11_BSS_ENTRY (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_entry.htm
tech.root: netvista
ms.assetid: 50661fc9-2f1f-4c9a-bc15-1cdf7c1f6d01
ms.date: 02/16/2018
keywords: ["DOT11_BSS_ENTRY structure"]
ms.keywords: "*PDOT11_BSS_ENTRY, DOT11_BSS_ENTRY, DOT11_BSS_ENTRY structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_f884f12d-d267-4ae3-b632-6c318b515880.xml, PDOT11_BSS_ENTRY, PDOT11_BSS_ENTRY structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_bss_entry, windot11/DOT11_BSS_ENTRY, windot11/PDOT11_BSS_ENTRY"
f1_keywords:
 - "windot11/DOT11_BSS_ENTRY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_BSS_ENTRY
targetos: Windows
req.typenames: DOT11_BSS_ENTRY, *PDOT11_BSS_ENTRY
product:
- Windows 10 or later.
---

# DOT11_BSS_ENTRY structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_BSS_ENTRY structure defines an IEEE 802.11 Beacon or Response Frame that the 802.11 station
  received during its last scan operation.


## -syntax


```cpp
typedef struct DOT11_BSS_ENTRY {
  ULONG                             uPhyId;
  DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO PhySpecificInfo;
  DOT11_MAC_ADDRESS                 dot11BSSID;
  DOT11_BSS_TYPE                    dot11BSSType;
  LONG                              lRSSI;
  ULONG                             uLinkQuality;
  BOOLEAN                           bInRegDomain;
  USHORT                            usBeaconPeriod;
  ULONGLONG                         ullTimestamp;
  ULONGLONG                         ullHostTimestamp;
  USHORT                            usCapabilityInformation;
  ULONG                             uBufferLength;
  UCHAR                             ucBuffer[1];
} DOT11_BSS_ENTRY, *PDOT11_BSS_ENTRY;
```


## -struct-fields




### -field uPhyId

The identifier (ID) of the PHY that the 802.11 station used to detect the BSS network. The PHY ID
     is the index within the list of supported PHYs returned by the driver through a query of
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a>.


This ID must not be DOT11_PHY_ID_ANY.


### -field PhySpecificInfo

The attributes of the PHY referenced by the
     <b>uPhyId</b> member.
     <b>PhySpecificInfo</b> is formatted as a
     <a href="..\windot11\ns-windot11-dot11_bss_entry_phy_specific_info.md">
     DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO</a> union.


### -field dot11BSSID

The media access control (MAC) address of the access point (AP) (for infrastructure BSS networks)
     or peer station (for independent BSS networks) that sent the 802.11 Beacon or Probe Response frame
     received by the 802.11 station while scanning. The data type for this member is the
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> structure.


### -field dot11BSSType

The BSS network type.


The data type for this member is the
     <a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a> enumeration. The miniport
     driver must not set this member to the
     <b>dot11_BSS_type_any</b> value.


### -field lRSSI

The received signal strength indicator (RSSI) value, in units of decibels referenced to 1.0
     milliwatts (dBm), as detected by the 802.11 station for the AP or peer station.


### -field uLinkQuality

The link quality value ranging from 0 through 100. A value of 100 specifies the highest link
     quality. For more information about determining the link quality, see
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/link-quality-operations">Link Quality Operations</a>.


### -field bInRegDomain

This member specifies whether the AP or peer station is operating within the regulatory domain as
     identified by the input country string. To set this member, the miniport driver must use the following
     guidelines:


<ul>
<li>
If the 802.11 station does not support multiple regulatory domains, set the member to <b>TRUE</b>. For
       more information about multiple regulatory domains, see
       <a href="https://docs.microsoft.com/previous-versions/ms893670(v=msdn.10)">
       OID_DOT11_MULTI_DOMAIN_CAPABILITY_IMPLEMENTED</a>.

</li>
<li>
If the input country string is all zeros, set the member to <b>TRUE</b>.

</li>
<li>
If the AP or peer station is not operating on a channel that is valid for the regulatory domain
       specified by the input country string, set the member to <b>FALSE</b>.

</li>
<li>
If the 802.11 Beacon or Probe Response frame, which was received from the AP or peer station,
       doesn't include a Country information element (IE), set the member to <b>TRUE</b>.

For more information about the Country IE, refer to Clause 7.3.2.12 of the IEEE 802.11d-2001
       standard.

</li>
<li>
If the 802.11 Beacon or Probe Response frame, which was received from the AP or peer station, does
       include a Country IE, set the member to <b>FALSE</b> if the value of the Country String subfield does not
       equal the input country string.

</li>
<li>
Set the member to <b>TRUE</b> in all other cases.

</li>
</ul>

### -field usBeaconPeriod

The value of the Beacon Interval field from the 802.11 Beacon or Probe Response frame.


### -field ullTimestamp

The value of the Timestamp field from the 802.11 Beacon or Probe Response frame.


### -field ullHostTimestamp

The timestamp, resolved through a call to
     <a href="..\ndis\nf-ndis-ndisgetcurrentsystemtime.md">NdisGetCurrentSystemTime</a>, which
     records when the 802.11 station received the 802.11 Beacon or Probe Response frame.


### -field usCapabilityInformation

The value of the Capability Information field from the 802.11 Beacon or Probe Response
     frame.


### -field uBufferLength

The length, in bytes, of the
     <b>ucBuffer</b> array in the DOT11_BSS_ENTRY structure.
     <b>ulBufferLength</b> must be the exact length of the data in the
     <b>ucBuffer</b> array and must not contain any padding for alignment.


### -field ucBuffer

The variable-length information elements (IEs) from the 802.11 Beacon or Probe Response frames.
     For each BSS, the IEs must be from the last Beacon or Probe Response frame received from that BSS
     network. If an IE is available in only one frame, the miniport driver must merge the IE with the other
     IEs from the last received Beacon or Probe Response frame.


When the NIC is in the Extensible Access Point (ExtAP) OP mode, the BSS list should contain an entry
     for the BSS that the NIC created.

For more information about the fields within IEEE 802.11 Beacon or Probe Response frames, refer to
     Clause 8.4 of the IEEE 802.11-2012 standard.


## -remarks



When the 802.11 station performs a scan operation, the Native 802.11 miniport driver caches the
    received 802.11 Beacon and Probe Response frames. For more information about the scan operation, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan
    Operations</a>.

After the 802.11 station completes the scan operation, the miniport driver returns the list of the
    cached Beacon and Probe Response frames when queried by
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-enum-bss-list">OID_DOT11_ENUM_BSS_LIST</a>. A separate
    DOT11_BSS_ENTRY structure is formatted for each Beacon and Probe Response frame.




## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>



<a href="..\wlclient\ns-wlclient-_dot11_bss_list.md">DOT11_BSS_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a>



<a href="https://docs.microsoft.com/previous-versions/ms893670(v=msdn.10)">
   OID_DOT11_MULTI_DOMAIN_CAPABILITY_IMPLEMENTED</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



<a href="..\windot11\ns-windot11-dot11_bss_entry_phy_specific_info.md">
   DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO</a>



<a href="..\ndis\nf-ndis-ndisgetcurrentsystemtime.md">NdisGetCurrentSystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-enum-bss-list">OID_DOT11_ENUM_BSS_LIST</a>



 

 


