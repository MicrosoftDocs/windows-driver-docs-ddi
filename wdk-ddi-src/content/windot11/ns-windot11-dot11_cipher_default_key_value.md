---
UID: NS:windot11.DOT11_CIPHER_DEFAULT_KEY_VALUE
title: DOT11_CIPHER_DEFAULT_KEY_VALUE (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_default_key_value.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_CIPHER_DEFAULT_KEY_VALUE structure"]
ms.keywords: "*PDOT11_CIPHER_DEFAULT_KEY_VALUE, DOT11_CIPHER_DEFAULT_KEY_VALUE, DOT11_CIPHER_DEFAULT_KEY_VALUE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_dba46983-b572-4b76-8628-776848e4b22e.xml, PDOT11_CIPHER_DEFAULT_KEY_VALUE, PDOT11_CIPHER_DEFAULT_KEY_VALUE structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_cipher_default_key_value, windot11/DOT11_CIPHER_DEFAULT_KEY_VALUE, windot11/PDOT11_CIPHER_DEFAULT_KEY_VALUE"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of the Windows operating   systems.
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
req.typenames: DOT11_CIPHER_DEFAULT_KEY_VALUE, *PDOT11_CIPHER_DEFAULT_KEY_VALUE
f1_keywords:
 - DOT11_CIPHER_DEFAULT_KEY_VALUE
 - windot11/DOT11_CIPHER_DEFAULT_KEY_VALUE
 - PDOT11_CIPHER_DEFAULT_KEY_VALUE
 - windot11/PDOT11_CIPHER_DEFAULT_KEY_VALUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_CIPHER_DEFAULT_KEY_VALUE
product:
 - Windows 10 or later.
---

# DOT11_CIPHER_DEFAULT_KEY_VALUE structure


## -description

> [!Important]
> The [Native 802.11 Wireless LAN](/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](/windows-hardware/drivers/network/wifi-universal-driver-model).

The DOT11_CIPHER_DEFAULT_KEY_VALUE structure defines a default cipher key or per-station default cipher key that will be added to or deleted from the key tables on the 802.11 station. For more information about these cipher key types, see [802.11 Cipher Key Types](/windows-hardware/drivers/network/802-11-cipher-key-types).

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_CIPHER_DEFAULT_KEY_VALUE structure. This member is
formatted as an [NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the members of *Header* to the following values:


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_CIPHER_DEFAULT_KEY_VALUE_REVISION_1.



#### Size

This member must be set to `sizeof(DOT11_CIPHER_DEFAULT_KEY_VALUE)`.

For more information about these members, see [NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md).

### -field uKeyIndex

The index of the key in the 802.11 station's default key array.

For standard 802.11 cipher algorithms, **uKeyIndex** must be from 0 through 3. For a cipher algorithm developed by an IHV, **uKeyIndex** can be any value within the range defined by the IHV.

For BIP **uKeyIndex** must be 4 or 5.

The IEEE 802.11-2012 standard defines default key index values from 1 through 4. The value *x* specified by this member maps to the 802.11 default key index (*x* + 1).

### -field AlgorithmId

The value of the cipher algorithm that uses this key. For more information about values for cipher algorithms, see [DOT11_CIPHER_ALGORITHM](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md).

For BIP, this should be set to DOT11_CIPHER_ALGO_BIP to pre-set the initial IGTK packet number.

The miniport driver must ignore this member if **bDelete** is **TRUE**.

### -field MacAddr

The media access control (MAC) address, which identifies the default key table to add or remove the key.


If the **dot11DesiredBSSType** management information base (MIB) object is set to **dot11_BSS_type_infrastructure**, the 802.11 station adds or removes the key from the default key
table regardless of the value of the **MacAddr** member. If the key is dynamically obtained from the access point (AP) the station is associated with, the **MacAddr** member will contain the AP's MAC address. Otherwise, **MacAddr** will have a value of 0x000000000000.

If the **dot11DesiredBSSType** management information base (MIB) object is set to **dot11_BSS_type_independent**, the 802.11 station must add or remove the key in the following way:

* If the value of this member is 0x000000000000, the 802.11 station adds or removes the key from the default key table. When the NIC is in the Extensible Access Point (ExtAP) OP mode, this value is zero.

* If the value of this member is a valid unicast MAC address, the 802.11 station adds or removes the key from the per-station default key table for the peer station in an independent BSS (IBSS) network with a MAC address equal to the value of **MacAddr** .

If a per-station default key table does not exist for the value of **MacAddr**, the 802.11 station must use any unused per-station default key table.

For more information about the **dot11DesiredBSSType** MIB object, see [OID_DOT11_DESIRED_BSS_TYPE](/windows-hardware/drivers/network/oid-dot11-desired-bss-type).

### -field bDelete

A Boolean value that specifies whether the miniport driver should delete the default key.

If set to **TRUE**, the miniport driver must delete the default key referenced by **uKeyIndex**. If set to **FALSE**, the miniport driver must add or update the default key referenced by **uKeyIndex** .

### -field bStatic

A Boolean value that specifies whether the miniport driver should delete the default key following
a connection or roaming operation.

If set to **FALSE**, the miniport driver must delete the default key referenced by **uKeyIndex** whenever the 802.11 station:

* Disconnects from the basic service set (BSS) network.
* Roams to a new BSS network.
* Reconnects to the same BSS network. 

If set to **TRUE**, the default key referenced by **uKeyIndex** must not be deleted unless it is:

* Explicitly deleted through a set request of [OID_DOT11_CIPHER_DEFAULT_KEY](/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id).
* Implicitly deleted through a method request of [OID_DOT11_RESET_REQUEST](/windows-hardware/drivers/network/oid-dot11-reset-request).


### -field usKeyLength

The length, in bytes, of the key material in the **ucKey** array.

### -field ucKey

The key material.

If **AlgorithmId** is set to **DOT11_CIPHER_ALGO_TKIP**, the **ucKey** array defines the key material through the [DOT11_KEY_ALGO_TKIP_MIC](..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md) structure.

If **AlgorithmId** is set to **DOT11_CIPHER_ALGO_CCMP**, the **ucKey** array defines the key material through the [DOT11_KEY_ALGO_CCMP](..\windot11\ns-windot11-dot11_key_algo_ccmp.md) structure.

If **AlgorithmId** is set to **DOT11_CIPHER_ALGO_BIP**, the **ucKey** array defines the key material through the [DOT11_KEY_ALGO_BIP](..\windot11\ns-windot11-dot11_key_algo_bip.md) structure.

## -syntax

```cpp
typedef struct DOT11_CIPHER_DEFAULT_KEY_VALUE {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uKeyIndex;
  DOT11_CIPHER_ALGORITHM AlgorithmId;
  DOT11_MAC_ADDRESS      MacAddr;
  BOOLEAN                bDelete;
  BOOLEAN                bStatic;
  USHORT                 usKeyLength;
  UCHAR                  ucKey[1];
} DOT11_CIPHER_DEFAULT_KEY_VALUE, *PDOT11_CIPHER_DEFAULT_KEY_VALUE;
```

## -remarks

If the **bDelete** member is **TRUE**, the following members are not valid and must be ignored:

* **bStatic**
* **usKeyLength**
* **ucKey**

## -see-also

[DOT11_KEY_ALGO_TKIP_MIC](..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md)



[OID_DOT11_RESET_REQUEST](/windows-hardware/drivers/network/oid-dot11-reset-request)



[DOT11_CIPHER_ALGORITHM](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md)



[OID_DOT11_CIPHER_DEFAULT_KEY](/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id)



[OID_DOT11_DESIRED_BSS_TYPE](/windows-hardware/drivers/network/oid-dot11-desired-bss-type)



[DOT11_KEY_ALGO_CCMP](..\windot11\ns-windot11-dot11_key_algo_ccmp.md)



[NDIS_OBJECT_HEADER](..\ntddndis\ns-ntddndis-_ndis_object_header.md)
