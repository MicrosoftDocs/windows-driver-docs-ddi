---
UID: NS:windot11._DOT11_EXTAP_ATTRIBUTES
title: _DOT11_EXTAP_ATTRIBUTES (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_extap_attributes.htm
tech.root: netvista
ms.assetid: 0460357c-7180-45f0-a7ab-83c46c24ba68
ms.date: 02/16/2018
keywords: ["DOT11_EXTAP_ATTRIBUTES structure"]
ms.keywords: "*PDOT11_EXTAP_ATTRIBUTES, DOT11_EXTAP_ATTRIBUTES, DOT11_EXTAP_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_a1779e69-266e-4fa0-bbd2-01701b9b8772.xml, PDOT11_EXTAP_ATTRIBUTES, PDOT11_EXTAP_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _DOT11_EXTAP_ATTRIBUTES, netvista.dot11_extap_attributes, windot11/DOT11_EXTAP_ATTRIBUTES, windot11/PDOT11_EXTAP_ATTRIBUTES"
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
req.typenames: DOT11_EXTAP_ATTRIBUTES, *PDOT11_EXTAP_ATTRIBUTES
f1_keywords:
 - _DOT11_EXTAP_ATTRIBUTES
 - windot11/_DOT11_EXTAP_ATTRIBUTES
 - PDOT11_EXTAP_ATTRIBUTES
 - windot11/PDOT11_EXTAP_ATTRIBUTES
 - DOT11_EXTAP_ATTRIBUTES
 - windot11/DOT11_EXTAP_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_EXTAP_ATTRIBUTES
product:
 - Windows 10 or later.
---

# _DOT11_EXTAP_ATTRIBUTES structure


## -description

> [!Important] 
> The [Native 802.11 Wireless LAN](/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](/windows-hardware/drivers/network/wifi-universal-driver-model).

The DOT11_EXTAP_ATTRIBUTES structure defines the physical and operating attributes of the miniport driver and 802.11 station when it operates in Extensible Access Point (ExtAP) mode.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_EXTAP_ATTRIBUTES structure. This member is formatted as an [NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md) structure.


The miniport driver must set the members of **Header** to the following values:


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_EXTAP_ATTRIBUTES_REVISION_1.

#### Size

This member must be set to **sizeof**(DOT11_EXTAP_ATTRIBUTES).

For more information about these members, see [NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md).

### -field uScanSSIDListSize

The maximum number of service set identifiers (SSIDs) supported by the 802.11 station for scan operations. The 802.11 station must support an SSID list of at least four entries.

The SSID list that the 802.11 station uses for scanning is specified when [OID_DOT11_SCAN_REQUEST](/windows-hardware/drivers/network/oid-dot11-scan-request) is set.

### -field uDesiredSSIDListSize

The maximum number of entries in the desired list of basic service set identifiers (BSSIDs)supported by the 802.11 station. The 802.11 station must support a BSSID list with at least one entry.


For more information about the desired BSSID list, see [OID_DOT11_DESIRED_BSSID_LIST](/windows-hardware/drivers/network/oid-dot11-desired-bssid-list).

### -field uPrivacyExemptionListSize

The maximum number of entries in the privacy exemption list supported by the 802.11 station. The
802.11 station must support a privacy exemption list with at least one entry.

For more information about the privacy exemption list, see [OID_DOT11_PRIVACY_EXEMPTION_LIST](/windows-hardware/drivers/network/oid-dot11-privacy-exemption-list).

### -field uAssociationTableSize

The maximum number of associations that the 802.11 station can support simultaneously. The 802.11 station must support an association list that has at least one entry. A NIC should typically be able to support at least 32 associations simultaneously.


If the NIC supports any authentication and cipher algorithms that require [key-Mapping keys](/windows-hardware/drivers/network/key-mapping-keys), it must support at least the number of entries in its key-mapping key table.

### -field uDefaultKeyTableSize

The maximum number of cipher keys the 802.11 station supports for the default key and per-station
default key tables.

For standard 802.11 cipher algorithms, the 802.11 station must support a table size of at least four cipher keys. For cipher algorithms developed by the independent hardware vendor (IHV), the table size can be four or greater.

### -field uWEPKeyValueMaxLength

The maximum length, in bytes, of a WEP cipher key supported by the 802.11 station.

The following table lists the minimum and maximum key lengths, in bytes, for the various WEP cipher values defined through DOT11_CIPHER_ALGORITHM(..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md).

|WEP cipher|Minimum key length|Maximum key length|
|--- |--- |--- |
|**DOT11_CIPHER_ALGO_WEP40**|5|5|
|**DOT11_CIPHER_ALGO_WEP104**|13|13|
|**DOT11_CIPHER_ALGO_WEP**|13|Any length supported by the 802.11 station|

### -field bStrictlyOrderedServiceClassImplemented

A Boolean value that, if set to **TRUE**, specifies that the 802.11 station supports the IEEE 802.11 StrictlyOrdered service class for media access control (MAC) service data unit (MSDU) packet delivery.

For more information about the StrictlyOrdered service class, refer to Clause 5.1.3 of the IEEE 802.11-2012 standard.

### -field uNumSupportedCountryOrRegionStrings

The number of country or region strings supported by the 802.11 station. If the 802.11 station supports multiple regulatory domains as specified by the IEEE 802.11d-2001 standard, each country or region string identifies a regulatory domain supported by the 802.11 station.

If the 802.11 station does not support the IEEE 802.11d-2001 standard, the miniport driver must set **uNumSupportedCountryOrRegionStrings** to zero.

### -field pSupportedCountryOrRegionStrings

A pointer to an array of 802.11d country or region strings that are supported by the 802.11
station. Each entry in the array is formatted as a [DOT11_COUNTRY_OR_REGION_STRING](/windows-hardware/drivers/network/oid-dot11-desired-country-or-region-string) structure.

### -field uInfraNumSupportedUcastAlgoPairs

The number of authentication and cipher algorithms supported by the 802.11 station for sending and receiving unicast packets when configured for operation in an infrastructure basic service set (BSS) network. The **uInfraNumSupportedUcastAlgoPairs** member must be the number of [DOT11_AUTH_CIPHER_PAIR](..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md) structures in the array referenced by the **pInfraSupportedUcastAlgoPairs** member.

### -field pInfraSupportedUcastAlgoPairs

A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for sending and receiving unicast packets in an infrastructure BSS network. Each entry in the array is formatted as a [DOT11_AUTH_CIPHER_PAIR](..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md) structure.

### -field uInfraNumSupportedMcastAlgoPairs

The number of authentication and cipher algorithms supported by the 802.11 station for sending and receiving multicast and broadcast packets when configured for operation in an infrastructure basic service set (BSS) network. The **uInfraNumSupportedMcastAlgoPairs** member must be the number of [DOT11_AUTH_CIPHER_PAIR](..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md) structures in the array referenced by the **pInfraSupportedMcastAlgoPairs** member.

### -field pInfraSupportedMcastAlgoPairs

A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for sending and receiving multicast and broadcast packets in an infrastructure BSS network. Each entry in the array is formatted as a [DOT11_AUTH_CIPHER_PAIR](..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md) structure.

## -syntax

```cpp
typedef struct _DOT11_EXTAP_ATTRIBUTES {
  NDIS_OBJECT_HEADER              Header;
  ULONG                           uScanSSIDListSize;
  ULONG                           uDesiredSSIDListSize;
  ULONG                           uPrivacyExemptionListSize;
  ULONG                           uAssociationTableSize;
  ULONG                           uDefaultKeyTableSize;
  ULONG                           uWEPKeyValueMaxLength;
  BOOLEAN                         bStrictlyOrderedServiceClassImplemented;
  ULONG                           uNumSupportedCountryOrRegionStrings;
  PDOT11_COUNTRY_OR_REGION_STRING pSupportedCountryOrRegionStrings;
  ULONG                           uInfraNumSupportedUcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedUcastAlgoPairs;
  ULONG                           uInfraNumSupportedMcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedMcastAlgoPairs;
} DOT11_EXTAP_ATTRIBUTES, *PDOT11_EXTAP_ATTRIBUTES;
```

## -see-also

[OID_DOT11_DESIRED_BSSID_LIST](/windows-hardware/drivers/network/oid-dot11-desired-bssid-list)


[DOT11_EXTAP_ATTRIBUTES](..\windot11\ns-windot11-_dot11_extap_attributes.md)



[DOT11_COUNTRY_OR_REGION_STRING](/windows-hardware/drivers/network/oid-dot11-desired-country-or-region-string)



[DOT11_AUTH_CIPHER_PAIR](..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md)



[DOT11_CIPHER_ALGORITHM](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md)



[OID_DOT11_PRIVACY_EXEMPTION_LIST](/windows-hardware/drivers/network/oid-dot11-privacy-exemption-list)



[OID_DOT11_SCAN_REQUEST](/windows-hardware/drivers/network/oid-dot11-scan-request)



[NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md)