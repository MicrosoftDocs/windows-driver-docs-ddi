---
UID: NS:windot11.DOT11_CIPHER_ALGORITHM_LIST
title: DOT11_CIPHER_ALGORITHM_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_algorithm_list.htm
tech.root: netvista
ms.assetid: b6d96a82-f744-4663-8373-886f4245c106
ms.date: 02/16/2018
keywords: ["DOT11_CIPHER_ALGORITHM_LIST structure"]
ms.keywords: "*PDOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_704d7a5a-0cf5-459f-af0c-06dfdc936a9e.xml, PDOT11_CIPHER_ALGORITHM_LIST, PDOT11_CIPHER_ALGORITHM_LIST structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_cipher_algorithm_list, windot11/DOT11_CIPHER_ALGORITHM_LIST, windot11/PDOT11_CIPHER_ALGORITHM_LIST"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.typenames: DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST
f1_keywords:
 - DOT11_CIPHER_ALGORITHM_LIST
 - windot11/DOT11_CIPHER_ALGORITHM_LIST
 - PDOT11_CIPHER_ALGORITHM_LIST
 - windot11/PDOT11_CIPHER_ALGORITHM_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_CIPHER_ALGORITHM_LIST
product:
 - Windows 10 or later.
---

# DOT11_CIPHER_ALGORITHM_LIST structure


## -description

> [!Important] 
> The [Native 802.11 Wireless LAN](/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](/windows-hardware/drivers/network/wifi-universal-driver-model).

The DOT11_CIPHER_ALGORITHM_LIST structure defines a list of [DOT11_CIPHER_ALGORITHM](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md) structures that can be enabled on the 802.11 station.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_CIPHER_ALGORITHM_LIST structure. This member is formatted as an [NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the members of **Header** to the following values:


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_CIPHER_ALGORITHM_LIST_REVISION_1.



#### Size

This member must be set to sizeof(DOT11_CIPHER_ALGORITHM_LIST).

For more information about these members, see [NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md).

### -field uNumOfEntries

The number of entries in the **AlgorithmIds** array.

### -field uTotalNumOfEntries

The maximum number of entries that the **AlgorithmIds** array can contain.

### -field AlgorithmIds

The cipher algorithm, which is defined by a [DOT11_CIPHER_ALGORITHM](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md) enumerator value.

The list of cipher algorithms is sorted by preference. **AlgorithmIds** [0] defines the cipher algorithm with the highest preference.

## -syntax

```cpp
typedef struct DOT11_CIPHER_ALGORITHM_LIST {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uNumOfEntries;
  ULONG                  uTotalNumOfEntries;
  DOT11_CIPHER_ALGORITHM AlgorithmIds[1];
} DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST;
```

## -remarks

A miniport driver returns the DOT11_CIPHER_ALGORITHM_LIST structure when it is queried by either [OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR](/previous-versions/windows/embedded/gg157261(v=winembedded.80)) or [OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR](/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair).

When these OIDs are queried, the miniport driver must verify that the **InformationBuffer** member of the [MiniportOidRequest](..\ndis\nc-ndis-miniport_oid_request.md) function's *OidRequest* parameter is large enough to return the entire DOT11_CIPHER_ALGORITHM_LIST structure, including all entries in the
**AlgorithmIds** array. The value of the **InformationBufferLength** member of the *OidRequest* parameter determines what the miniport driver must do, as the following list shows:

* If the value of the **InformationBufferLength** member is less than the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following:
  * For the _OidRequest_ parameter, set the **BytesWritten** member to zero and the **BytesNeeded** member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST structure.
  * Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its [MiniportOidRequest](..\ndis\nc-ndis-miniport_oid_request.md) function.
* If the value of the **InformationBufferLength** member is greater than or equal to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following to complete a successful query request:
  * For the DOT11_CIPHER_ALGORITHM_LIST structure, set the **uNumOfEntries** and **uTotalNumOfEntries** members to the total number of entries in the **AlgorithmIds** array.
  * For the _OidRequest_ parameter, set the **BytesNeeded** member to zero and the **BytesWritten** member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST structure. The miniport driver must also copy the entire DOT11_CIPHER_ALGORITHM_LIST structure to the **InformationBuffer** member.
  * Return NDIS_STATUS_SUCCESS from its [MiniportOidRequest](..\ndis\nc-ndis-miniport_oid_request.md) function.

## -see-also

[OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR](/previous-versions/windows/embedded/gg157261(v=winembedded.80))



[OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR](/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair)


[DOT11_CIPHER_ALGORITHM](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md)


[NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md)
