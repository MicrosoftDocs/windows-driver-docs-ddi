---
UID: NS:windot11._DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
title: _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST (windot11.h)
description: the DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure is included with a OID_DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST request. The structure contains the list of secondary device types advertised by a Wi-Fi Direct device.
old-location: netvista\_dot11_wfd_secondary_device_type_list.htm
tech.root: netvista
ms.assetid: ABD61A6C-EE0A-49AF-AE8C-75014C2A09D4
ms.date: 02/16/2018
keywords: ["_DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure"]
ms.keywords: "*PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, netvista._dot11_wfd_secondary_device_type_list, windot11/ DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, windot11/PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST"
f1_keywords:
 - "windot11/DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST"
 - "DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST"
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
- DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
targetos: Windows
req.typenames: DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, *PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
product:
- Windows 10 or later.
---

# _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>the <b>DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST</b> structure is included with a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-secondary-device-type-list">OID_DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST</a> request. The structure contains the list of secondary device types advertised by a Wi-Fi Direct device.


## -syntax


```cpp
typedef struct _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 uNumOfEntries;
  ULONG                 uTotalNumOfEntries;
  DOT11_WFD_DEVICE_TYPE SecondaryDeviceTypes[1];
}  DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, *PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST;
```


## -struct-fields




### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_SECONDARY_DEVICE_TYPE_LIST_REVISION_1</td>
</tr>
</table>
 


### -field uNumOfEntries

The number of entries present in <b>SecondaryDeviceTypes</b>.


### -field uTotalNumOfEntries

The maximum number of entries the <b>SecondaryDeviceTypes</b> array can contain.


### -field SecondaryDeviceTypes

An array of secondary device types.

