---
UID: NS:windot11.DOT11_VWIFI_ATTRIBUTES
title: DOT11_VWIFI_ATTRIBUTES (windot11.h)
description: The DOT11_VWIFI_ATTRIBUTES structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_vwifi_attributes.htm
tech.root: netvista
ms.date: 03/07/2024
keywords: ["DOT11_VWIFI_ATTRIBUTES structure"]
ms.keywords: "*PDOT11_VWIFI_ATTRIBUTES, DOT11_VWIFI_ATTRIBUTES, DOT11_VWIFI_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_fdecf787-d328-4546-a4fc-ac7205851ebf.xml, PDOT11_VWIFI_ATTRIBUTES, PDOT11_VWIFI_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_vwifi_attributes, windot11/DOT11_VWIFI_ATTRIBUTES, windot11/PDOT11_VWIFI_ATTRIBUTES"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   system.
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
req.typenames: DOT11_VWIFI_ATTRIBUTES, *PDOT11_VWIFI_ATTRIBUTES
f1_keywords:
 - DOT11_VWIFI_ATTRIBUTES
 - windot11/DOT11_VWIFI_ATTRIBUTES
 - PDOT11_VWIFI_ATTRIBUTES
 - windot11/PDOT11_VWIFI_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_VWIFI_ATTRIBUTES
 - PDOT11_VWIFI_ATTRIBUTES
---

# DOT11_VWIFI_ATTRIBUTES structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_VWIFI_ATTRIBUTES structure defines the virtualization attributes of the miniport driver and
  802.11 station when operating in Virtual WiFi mode.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_VWIFI_ATTRIBUTES structure. This member is formatted as
     an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_VWIFI_ATTRIBUTES_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_VWIFI_ATTRIBUTES).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field Combinations[*]

The maximum number of entries that the
     <b>Combinations</b> array can contain.

### -field Combinations[1]

The list of supported combinations of 802.11 MAC entities that an 802.11 miniport driver can
     simultaneously support when it is virtualized. Each entry in this list is specified through an array of
     <a href="..\windot11\ns-windot11-_dot11_vwifi_combination.md">DOT11_VWIFI_COMBINATION</a>,  <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v2.md">
     DOT11_VWIFI_COMBINATION_V2</a>, or <a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v3.md">DOT11_VWIFI_COMBINATION_V3</a> structures.

## -see-also

<a href="..\windot11\ns-windot11-_dot11_vwifi_combination.md">DOT11_VWIFI_COMBINATION</a>



<a href="..\windot11\ns-windot11-_dot11_vwifi_combination_v2.md">DOT11_VWIFI_COMBINATION_V2</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>

