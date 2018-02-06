---
UID: NS:windot11._DOT11_SCAN_REQUEST_V2
title: "_DOT11_SCAN_REQUEST_V2"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_scan_request_v2.htm
old-project: netvista
ms.assetid: fd6dd2f4-ee58-46da-ba87-5aecaff35dd0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Native_802.11_data_types_e7a02ffc-ecf6-4159-ab3d-85c87d844785.xml, netvista.dot11_scan_request_v2, windot11/PDOT11_SCAN_REQUEST_V2, PDOT11_SCAN_REQUEST_V2, DOT11_SCAN_REQUEST_V2 structure [Network Drivers Starting with Windows Vista], _DOT11_SCAN_REQUEST_V2, windot11/DOT11_SCAN_REQUEST_V2, *PDOT11_SCAN_REQUEST_V2, PDOT11_SCAN_REQUEST_V2 structure pointer [Network Drivers Starting with Windows Vista], DOT11_SCAN_REQUEST_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_SCAN_REQUEST_V2
product: Windows
targetos: Windows
req.typenames: "*PDOT11_SCAN_REQUEST_V2, DOT11_SCAN_REQUEST_V2"
req.product: Windows 10 or later.
---

# _DOT11_SCAN_REQUEST_V2 structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SCAN_REQUEST_V2 structure defines the parameters for the explicit scan operation performed
  by the 802.11 station. The station performs the explicit scan operation following an OID set request of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>.


## -syntax


````
typedef struct _DOT11_SCAN_REQUEST_V2 {
  DOT11_BSS_TYPE    dot11BSSType;
  DOT11_MAC_ADDRESS dot11BSSID;
  DOT11_SCAN_TYPE   dot11ScanType;
  BOOLEAN           bRestrictedScan;
  ULONG             udot11SSIDsOffset;
  ULONG             uNumOfdot11SSIDs;
  BOOLEAN           bUseRequestIE;
  ULONG             uRequestIDsOffset;
  ULONG             uNumOfRequestIDs;
  ULONG             uPhyTypeInfosOffset;
  ULONG             uNumOfPhyTypeInfos;
  ULONG             uIEsOffset;
  ULONG             uIEsLength;
  UCHAR             ucBuffer[1];
} DOT11_SCAN_REQUEST_V2, *PDOT11_SCAN_REQUEST_V2;
````


## -struct-fields




### -field dot11BSSType

The type of basic service set (BSS) networks for which the 802.11 station scans. The data type for
     this member is the 
     <a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a> enumeration.


### -field dot11BSSID

The BSS identifier (BSSID) of a BSS network for which the 802.11 station scans. If this member is
     set to the wildcard BSSID (0xFFFFFFFFFFFF), the station scans for all BSSIDs.


### -field dot11ScanType

The type of scan that the 802.11 station performs. The data type for this member is the
     DOT11_SCAN_TYPE enumeration, which declares the following values:
     



Regardless of the value of 
     <b>dot11ScanType</b>, the 802.11 station must perform a scan type of 
     <b>dot11_scan_type_passive</b> whenever it scans on channels that are not valid in the current regulatory
     domain. Also, the 802.11 station must perform a scan type of 
     <b>dot11_scan_type_passive</b> if it does not have a default regulatory domain. For more information
     about regulatory domains, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-current-reg-domain">
     OID_DOT11_CURRENT_REG_DOMAIN</a>.

If the 
     <b>dot11_scan_type_forced</b> bit is set in the 
     <b>dot11ScanType</b> member, the 802.11 station must perform a complete scan on every supported channel.
     If the 
     <b>dot11_scan_type_forced</b> bit is not set, the 802.11 station can perform a complete scan, or it can
     perform a partial scan on a subset of the supported channels.
<div class="alert"><b>Note</b>  The 
     <b>dot11_scan_type_forced</b> bit is only supported when the miniport driver is operating in Extensible
     Station (ExtSTA) mode. The 
     <b>dot11_scan_type_forced</b> bit must be set through a bitwise OR with a DOT11_SCAN_TYPE
     value.</div><div> </div>

#### dot11_scan_type_active

The station transmits an 802.11 Probe Request frame on each channel that it scans. It dwells on
       the channel long enough to receive 802.11 Probe Response frames for its Probe Request. The station
       also receives 802.11 Beacon frames sent on the channel.


#### dot11_scan_type_passive

The station does not transmit an 802.11 Probe Request frame on each channel that it scans.
       Instead, it receives 802.11 Beacon or Probe Request frames sent on the channel.


#### dot11_scan_type_auto

The station can perform active or passive scans, or it can use a combination of both scan
       types.


### -field bRestrictedScan

If this member is <b>TRUE</b>, the 802.11 station performs a scan restricted to the channel and PHY
     configuration used to connect to a BSS network.
     

The miniport driver must ignore this member if any of the following are true:
<ul>
<li>
The miniport driver is operating in ExtSTA mode.

</li>
<li>
The 802.11 station is not connected to a BSS network.

</li>
</ul>

### -field udot11SSIDsOffset

The offset in the 
     <b>ucBuffer</b> array where the service set identifier (SSID) list begins. Each entry in the SSID list is
     formatted as a 
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a> structure.
     

The 802.11 station scans for each SSID in the list. For example, if 
     <b>dot11ScanType</b> is set to 
     <b>dot11_scan_type_active</b>, the 802.11 station transmits an 802.11 Probe Request for each SSID in the
     list while scanning on a channel.


### -field uNumOfdot11SSIDs

The number of entries in the SSID list.
     

If 
     <b>uNumOfdot11SSIDs</b> is zero, the miniport driver must use an SSID list containing the wildcard
     zero-length SSID.


### -field bUseRequestIE

If this member is <b>TRUE</b>, the 802.11 station must include the list of request IDs (defined through
     the 
     <b>uRequestIDsOffset</b> and 
     <b>uNumOfRequestIDs</b> members) within the 802.11d request information element (IE) of each Probe
     Request frame that it transmits during the active scan.
     

The miniport driver must ignore this member (along with the 
     <b>uRequestIDsOffset</b> and 
     <b>uNumOfRequestIDs</b> members) if any of the following are true:
<ul>
<li>
The miniport driver is operating in ExtSTA mode.

</li>
<li>
The 802.11 
       <b>dot11MultiDomainCapabilityEnabled</b> management information base (MIB) object is <b>FALSE</b>. For more
       information about the 
       <b>dot11MultiDomainCapabilityEnabled</b> MIB object, see 
       <a href="https://msdn.microsoft.com/en-us/library/ee486712.aspx">
       OID_DOT11_MULTI_DOMAIN_CAPABILITY_ENABLED</a>.

</li>
<li>
The 
       <b>dot11ScanType</b> member is set to 
       <b>dot11_scan_type_passive</b>.

</li>
</ul>

### -field uRequestIDsOffset

The offset in the 
     <b>ucBuffer</b> array where the Request IDs list begins. Each entry in the request IDs list is formatted
     as a UCHAR data type.


### -field uNumOfRequestIDs

The number of entries in the request IDs list.


### -field uPhyTypeInfosOffset

The offset in the 
     <b>ucBuffer</b> array where the list of PHY types begins. Each entry in the list of PHY types is
     formatted as a 
     <a href="..\windot11\ns-windot11-_dot11_phy_type_info.md">DOT11_PHY_TYPE_INFO</a> structure.
     

The 802.11 station must perform the BSS scan by using each of the specified PHY types from this
     list.

The miniport driver must ignore this member (along with the 
     <b>uNumOfPhyTypeInfos</b> member) if 
     <b>bRestrictedScan</b> is set to <b>TRUE</b>.


### -field uNumOfPhyTypeInfos

The number of entries in the list of PHY types.
     

If 
     <b>uNumOfPhyTypeInfos</b> is zero, the 802.11 station performs the scan using all of its supported
     PHYs.


### -field uIEsOffset

The offset in the 
     <b>ucBuffer</b> array where the list of variable-length information elements (IEs) begins. The 802.11
     station must append the list of IEs to the end of each Probe Request frame that it transmits during an
     active scan.
     

The miniport driver must ignore this member (along with the 
     <b>uIEsLength</b> member) if 
     <b>dot11ScanType</b> is set to 
     <b>dot11_scan_type_passive</b>.


### -field uIEsLength

The length, in bytes, of the list of IEs.


### -field ucBuffer

The buffer containing optional data as specified through other members of this structure.


## -remarks


The 802.11 station performs explicit scan operations following the OID set request of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>. The station
    performs the scan operation by using the parameters defined through the DOT11_SCAN_REQUEST_V2, which
    accompanies the set request.

For more information about the scan operations performed by a Native 802.11 miniport driver, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan
    Operations</a>.

For more information about the ExtSTA operation mode, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/extensible-station-operation-mode">Extensible Station Operation
    Mode</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>

<a href="..\windot11\ns-windot11-_dot11_phy_type_info.md">DOT11_PHY_TYPE_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SCAN_REQUEST_V2 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

