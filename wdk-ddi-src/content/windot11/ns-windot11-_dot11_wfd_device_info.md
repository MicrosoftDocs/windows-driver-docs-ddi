---
UID: NS:windot11._DOT11_WFD_DEVICE_INFO
title: _DOT11_WFD_DEVICE_INFO (windot11.h)
description: the DOT11_WFD_DEVICE_INFO structure is included with a OID_DOT11_WFD_DEVICE_INFO request. The structure contains Wi-Fi Direct (WFD) device information related to Peer-to-Peer (P2P) attributes.
old-location: netvista\_dot11_wfd_device_info.htm
tech.root: netvista
ms.assetid: 6E0E9BC9-9C84-4511-A28E-2BB2D6367F74
ms.date: 02/16/2018
ms.keywords: "*PDOT11_WFD_DEVICE_INFO, DOT11_WFD_DEVICE_INFO, DOT11_WFD_DEVICE_INFO structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DEVICE_INFO, PDOT11_WFD_DEVICE_INFO structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DEVICE_INFO, netvista._dot11_wfd_device_info, windot11/ DOT11_WFD_DEVICE_INFO, windot11/PDOT11_WFD_DEVICE_INFO"
ms.topic: struct
f1_keywords:
 - "windot11/DOT11_WFD_DEVICE_INFO"
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
- DOT11_WFD_DEVICE_INFO
product:
- Windows
targetos: Windows
req.typenames: DOT11_WFD_DEVICE_INFO, *PDOT11_WFD_DEVICE_INFO
product:
- Windows 10 or later.
---

# _DOT11_WFD_DEVICE_INFO structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>the <b>DOT11_WFD_DEVICE_INFO</b> structure is included with a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-device-info">OID_DOT11_WFD_DEVICE_INFO</a> request. The structure contains  Wi-Fi Direct (WFD) device information related to Peer-to-Peer (P2P) attributes.


## -syntax


```cpp
typedef struct _DOT11_WFD_DEVICE_INFO {
  NDIS_OBJECT_HEADER    Header;
  DOT11_MAC_ADDRESS     DeviceAddress;
  USHORT                ConfigMethods;
  DOT11_WPS_DEVICE_TYPE PrimaryDeviceType;
  DOT11_WPS_DEVICE_NAME DeviceName;
} DOT11_WFD_DEVICE_INFO, *PDOT11_WFD_DEVICE_INFO;
```


## -struct-fields




### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_DEVICE_INFO</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_WFD_DEVICE_INFO_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_DEVICE_INFO_REVISION_1</td>
</tr>
</table>
 


### -field DeviceAddress

The device address to assign to a WFD port. This address is used when constructing P2P Information Elements (IEs).


### -field ConfigMethods

The configuration methods supported by the WFD device.


### -field PrimaryDeviceType

The primary device type for the WFD device.


### -field DeviceName

A friendly name assigned to the WFD device.

