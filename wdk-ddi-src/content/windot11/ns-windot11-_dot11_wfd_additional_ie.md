---
UID: NS:windot11._DOT11_WFD_ADDITIONAL_IE
title: _DOT11_WFD_ADDITIONAL_IE (windot11.h)
description: The DOT11_WFD_ADDITIONAL_IE structure represents an additional Information Element (IE) included in an OID_DOT11_WFD_ADDITIONAL_IE request. An additional IE contains both request and response data for probe and beacon operations.
old-location: netvista\_dot11_wfd_additional_ie.htm
tech.root: netvista
ms.assetid: F381C8DB-DC69-4820-BDCE-2F1DF3482FDD
ms.date: 02/16/2018
ms.keywords: "*PDOT11_WFD_ADDITIONAL_IE, DOT11_WFD_ADDITIONAL_IE, DOT11_WFD_ADDITIONAL_IE structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_ADDITIONAL_IE, PDOT11_WFD_ADDITIONAL_IE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_ADDITIONAL_IE, netvista._dot11_wfd_additional_ie, windot11/ DOT11_WFD_ADDITIONAL_IE, windot11/PDOT11_WFD_ADDITIONAL_IE"
ms.topic: struct
f1_keywords:
 - "windot11/DOT11_WFD_ADDITIONAL_IE"
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
- DOT11_WFD_ADDITIONAL_IE
product:
- Windows
targetos: Windows
req.typenames: DOT11_WFD_ADDITIONAL_IE, *PDOT11_WFD_ADDITIONAL_IE
product:
- Windows 10 or later.
---

# _DOT11_WFD_ADDITIONAL_IE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_ADDITIONAL_IE</b> structure represents an additional Information Element (IE) included in an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-additional-ie">OID_DOT11_WFD_ADDITIONAL_IE</a> request. An additional IE contains both request and response data for probe and beacon operations.


## -syntax


```cpp
typedef struct _DOT11_WFD_ADDITIONAL_IE {
  NDIS_OBJECT_HEADER Header;
  ULONG              uBeaconIEsOffset;
  ULONG              uBeaconIEsLength;
  ULONG              uProbeResponseIEsOffset;
  ULONG              uProbeResponseIEsLength;
  ULONG              uDefaultRequestIEsOffset;
  ULONG              uDefaultRequestIEsLength;
}  DOT11_WFD_ADDITIONAL_IE, *PDOT11_WFD_ADDITIONAL_IE;
```


## -struct-fields




### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_ADDITIONAL_IE</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_WFD_ADDITIONAL_IE_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_ADDITIONAL_IE_REVISION_1</td>
</tr>
</table>
 


### -field uBeaconIEsOffset

The offset, in bytes, of an array of beacon IEs. This offset is relative to the start of the buffer that contains this structure. The Wi-Fi Direct (WFD) port must add these addition IEs to the beacon packets when it is acting as a Group Owner.


### -field uBeaconIEsLength

The length, in bytes, of the additional IEs at  <b>uBeaconIEsOffset</b>. This member is ignored when the WFD port is operating in device or client mode.


### -field uProbeResponseIEsOffset

The offset, in bytes, of an array of probe response IEs. This offset is relative to the start of the buffer that contains this structure. The Wi-Fi Direct (WFD) port must add these addition IEs to the probe response packets when it is acting as a WFD device or Group Owner.


### -field uProbeResponseIEsLength

The length, in bytes, of the additional IEs at  <b>uProbeResponseIEsOffset</b>. This member is ignored when the WFD port is operating in client mode.


### -field uDefaultRequestIEsOffset

The offset, in bytes, of an array of probe request IEs. This offset is relative to the start of the buffer that contains this structure. The Wi-Fi Direct (WFD) port must add these addition IEs to the probe request packets it transmits.


### -field uDefaultRequestIEsLength

The length, in bytes, of the additional IEs at  <b>uDefaultRequestIEsOffset</b>.


## -remarks



The additional IEs at  <b>uDefaultRequestIEsOffset</b> are for probe requests originating from the driver only. Explicit device discovery requests from the system are initiated in an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-discover-request">OID_DOT11_WFD_DISCOVER_REQUEST</a>. The IEs for an explicit discovery request should come from those IEs in the OID_DOT11_WFD_DISCOVER_REQUEST request and not from the IEs at <b>uDefaultRequestIEsOffset</b>.



