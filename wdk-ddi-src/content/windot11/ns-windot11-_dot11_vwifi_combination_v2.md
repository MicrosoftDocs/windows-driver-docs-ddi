---
UID: NS:windot11._DOT11_VWIFI_COMBINATION_V2
title: _DOT11_VWIFI_COMBINATION_V2 (windot11.h)
description: The DOT11_VWIFI_COMBINATION_V2 structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_vwifi_combination_v2.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_VWIFI_COMBINATION_V2 structure"]
ms.keywords: "*PDOT11_VWIFI_COMBINATION_V2, DOT11_VWIFI_COMBINATION_V2, DOT11_VWIFI_COMBINATION_V2 structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_1210442c-19be-406c-bec5-12ad170fc90b.xml, PDOT11_VWIFI_COMBINATION_V2, PDOT11_VWIFI_COMBINATION_V2 structure pointer [Network Drivers Starting with Windows Vista], _DOT11_VWIFI_COMBINATION_V2, netvista.dot11_vwifi_combination_v2, windot11/DOT11_VWIFI_COMBINATION_V2, windot11/PDOT11_VWIFI_COMBINATION_V2"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.typenames: DOT11_VWIFI_COMBINATION_V2, *PDOT11_VWIFI_COMBINATION_V2
f1_keywords:
 - _DOT11_VWIFI_COMBINATION_V2
 - windot11/_DOT11_VWIFI_COMBINATION_V2
 - PDOT11_VWIFI_COMBINATION_V2
 - windot11/PDOT11_VWIFI_COMBINATION_V2
 - DOT11_VWIFI_COMBINATION_V2
 - windot11/DOT11_VWIFI_COMBINATION_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_VWIFI_COMBINATION_V2
 - PDOT11_VWIFI_COMBINATION_V2
 - DOT11_VWIFI_COMBINATION_V2
---

# _DOT11_VWIFI_COMBINATION_V2 structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_VWIFI_COMBINATION_V2 structure specifies the combination of 802.11 MAC entities that an
  802.11 miniport driver can simultaneously support when it is virtualized.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_VWIFI_COMBINATION_V2 structure. This member is formatted
     as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_VWIFI_COMBINATION_REVISION_2.



#### Size

This member must be set to
       sizeof(DOT11_VWIFI_COMBINATION_V2).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field uNumInfrastructure

The number of 802.11 infrastructure stations supported. For more information, see the following
     Remarks section.

### -field uNumAdhoc

The number of Adhoc Stations supported. For more information, see the following Remarks
     section.

### -field uNumSoftAP

The number of Soft AP Stations supported. For more information, see the following Remarks
     section.

### -field uNumVirtualStation

The number of Virtual Stations supported. For more information, see the following Remarks
     section.

## -syntax

```cpp
typedef struct _DOT11_VWIFI_COMBINATION_V2 {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumInfrastructure;
  ULONG              uNumAdhoc;
  ULONG              uNumSoftAP;
  ULONG              uNumVirtualStation;
} DOT11_VWIFI_COMBINATION_V2, *PDOT11_VWIFI_COMBINATION_V2;
```

## -remarks

Starting with Windows 7, the 802.11 miniport driver must only report one or more of the following
    combinations of member values.

<b>No 802.11 Virtual Station
     </b>

<ul>
<li>
<b>uNumInfrastructure</b> = 1

</li>
<li>
<b>uNumAdhoc</b> = 0

</li>
<li>
<b>uNumSoftAP</b> = 1

</li>
<li>
<b>uNumVirtualStation</b> = 0

</li>
</ul>
<b>One 802.11 Virtual Station
     </b>

<ul>
<li>
<b>uNumInfrastructure</b> = 1

</li>
<li>
<b>uNumAdhoc</b> = 0

</li>
<li>
<b>uNumSoftAP</b> = 1

</li>
<li>
<b>uNumVirtualStation</b> = 1

</li>
</ul>

## -see-also

<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>

