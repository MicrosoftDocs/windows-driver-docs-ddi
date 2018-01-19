---
UID: NS:windot11.DOT11_DATA_RATE_MAPPING_ENTRY
title: DOT11_DATA_RATE_MAPPING_ENTRY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_data_rate_mapping_entry.htm
old-project: netvista
ms.assetid: d2772a9e-655a-4e3e-8b48-65d58b0a659d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_DATA_RATE_MAPPING_ENTRY, DOT11_DATA_RATE_MAPPING_ENTRY, *PDOT11_DATA_RATE_MAPPING_ENTRY
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
req.alt-api: DOT11_DATA_RATE_MAPPING_ENTRY
req.alt-loc: windot11.h
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
req.typenames: DOT11_DATA_RATE_MAPPING_ENTRY, *PDOT11_DATA_RATE_MAPPING_ENTRY
req.product: Windows 10 or later.
---

# DOT11_DATA_RATE_MAPPING_ENTRY structure



## -description

## -syntax

````
typedef struct DOT11_DATA_RATE_MAPPING_ENTRY {
  UCHAR  ucDataRateIndex;
  UCHAR  ucDataRateFlag;
  USHORT usDataRateValue;
} DOT11_DATA_RATE_MAPPING_ENTRY, *PDOT11_DATA_RATE_MAPPING_ENTRY;
````


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

1 Mbps

0x02

2 Mbps

0x04

3 Mbps

0x06

4.5 Mbps

0x09

5.5 Mbps

0x0B

6 Mbps

0x0C

9 Mbps

0x12

11 Mbps

0x16

12 Mbps

0x18

18 Mbps

0x24

22 Mbps

0x2C

24 Mbps

0x30

27 Mbps

0x36

33 Mbps

0x42

36 Mbps

0x48

48 Mbps

0x60

54 Mbps

0x6C


## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.oid_dot11_data_rate_mapping_table">
   OID_DOT11_DATA_RATE_MAPPING_TABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_DATA_RATE_MAPPING_ENTRY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

