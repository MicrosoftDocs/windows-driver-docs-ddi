---
UID: NS:windot11.DOT11_DATA_RATE_MAPPING_ENTRY
title: DOT11_DATA_RATE_MAPPING_ENTRY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_data_rate_mapping_entry.htm
tech.root: netvista
ms.assetid: d2772a9e-655a-4e3e-8b48-65d58b0a659d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_DATA_RATE_MAPPING_ENTRY, DOT11_DATA_RATE_MAPPING_ENTRY, DOT11_DATA_RATE_MAPPING_ENTRY structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_465aabe5-c790-4e3d-ae63-3313dd487eb5.xml, PDOT11_DATA_RATE_MAPPING_ENTRY, PDOT11_DATA_RATE_MAPPING_ENTRY structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_data_rate_mapping_entry, windot11/DOT11_DATA_RATE_MAPPING_ENTRY, windot11/PDOT11_DATA_RATE_MAPPING_ENTRY"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	windot11.h
api_name:
-	DOT11_DATA_RATE_MAPPING_ENTRY
product:
- Windows
targetos: Windows
req.typenames: DOT11_DATA_RATE_MAPPING_ENTRY, *PDOT11_DATA_RATE_MAPPING_ENTRY
product:
- Windows 10 or later.
---

# DOT11_DATA_RATE_MAPPING_ENTRY structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DATA_RATE_MAPPING_ENTRY structure defines a data rate supported by a PHY on the 802.11
  station for transmit and receive operations.


## -syntax


```cpp
typedef struct DOT11_DATA_RATE_MAPPING_ENTRY {
  UCHAR  ucDataRateIndex;
  UCHAR  ucDataRateFlag;
  USHORT usDataRateValue;
} DOT11_DATA_RATE_MAPPING_ENTRY, *PDOT11_DATA_RATE_MAPPING_ENTRY;
```


## -struct-fields




### -field ucDataRateIndex

The index value for the data rate contained in the
     <b>usDataRateValue</b> member. The value of the
     <b>ucDataRateIndex</b> member must be unique for each entry in the
     <b>DataRateMappingEntries</b> array.


This value is a bitmask as defined in the following table.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>
0-6

</td>
<td>
The data rate index, containing a value from 2 through127.

</td>
</tr>
<tr>
<td>
7

</td>
<td>
This bit is not used and must be set to zero.

</td>
</tr>
</table>
 


### -field ucDataRateFlag

The attributes of the data rate entry.


This value is a bitmask as defined in the following table.

<table>
<tr>
<th>Bits</th>
<th>Name</th>
<th>Description</th>
</tr>
<tr>
<td>
0

</td>
<td>
<b>DOT11_DATA_RATE_NON_STANDARD</b>

</td>
<td>
If set, the entry is not a standard data rate defined in IEEE 802.11 standards.

</td>
</tr>
<tr>
<td>
1-7

</td>
<td></td>
<td>
These bits are not used and must be set to zero.

</td>
</tr>
</table>
 


### -field usDataRateValue

The data rate, defined in units of 500 kilobits per second (Kbps), with a value from 0x0002 to
     0xFFFF.


## -remarks



For the IEEE 802.11 standard data rates, the miniport driver must set the
    <b>ucDataRateIndex</b> and
    <b>usDataRateValue</b> members to the same value.

The following table shows the IEEE 802.11 standard data rates, in units of megabits per second (Mbps),
    and the related values for the
    <b>ucDataRateIndex</b> and
    <b>usDataRateValue</b> members.

<table>
<tr>
<th>IEEE 802.11 Standard Rate</th>
<th>ucDataRateIndex</th>
<th>usDataRateValue</th>
</tr>
<tr>
<td>
1 Mbps

</td>
<td>
0x02

</td>
<td>
0x02

</td>
</tr>
<tr>
<td>
2 Mbps

</td>
<td>
0x04

</td>
<td>
0x04

</td>
</tr>
<tr>
<td>
3 Mbps

</td>
<td>
0x06

</td>
<td>
0x06

</td>
</tr>
<tr>
<td>
4.5 Mbps

</td>
<td>
0x09

</td>
<td>
0x09

</td>
</tr>
<tr>
<td>
5.5 Mbps

</td>
<td>
0x0B

</td>
<td>
0x0B

</td>
</tr>
<tr>
<td>
6 Mbps

</td>
<td>
0x0C

</td>
<td>
0x0C

</td>
</tr>
<tr>
<td>
9 Mbps

</td>
<td>
0x12

</td>
<td>
0x12

</td>
</tr>
<tr>
<td>
11 Mbps

</td>
<td>
0x16

</td>
<td>
0x16

</td>
</tr>
<tr>
<td>
12 Mbps

</td>
<td>
0x18

</td>
<td>
0x18

</td>
</tr>
<tr>
<td>
18 Mbps

</td>
<td>
0x24

</td>
<td>
0x24

</td>
</tr>
<tr>
<td>
22 Mbps

</td>
<td>
0x2C

</td>
<td>
0x2C

</td>
</tr>
<tr>
<td>
24 Mbps

</td>
<td>
0x30

</td>
<td>
0x30

</td>
</tr>
<tr>
<td>
27 Mbps

</td>
<td>
0x36

</td>
<td>
0x36

</td>
</tr>
<tr>
<td>
33 Mbps

</td>
<td>
0x42

</td>
<td>
0x42

</td>
</tr>
<tr>
<td>
36 Mbps

</td>
<td>
0x48

</td>
<td>
0x48

</td>
</tr>
<tr>
<td>
48 Mbps

</td>
<td>
0x60

</td>
<td>
0x60

</td>
</tr>
<tr>
<td>
54 Mbps

</td>
<td>
0x6C

</td>
<td>
0x6C

</td>
</tr>
</table>
 




## -see-also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
   OID_DOT11_DATA_RATE_MAPPING_TABLE</a>



 

 


