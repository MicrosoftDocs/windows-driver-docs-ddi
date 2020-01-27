---
UID: NS:windot11.DOT11_CIPHER_DEFAULT_KEY_VALUE
title: DOT11_CIPHER_DEFAULT_KEY_VALUE (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_default_key_value.htm
tech.root: netvista
ms.assetid: 7362b20a-6ec4-4b22-8981-3a4b647a3cfa
ms.date: 02/16/2018
ms.keywords: "*PDOT11_CIPHER_DEFAULT_KEY_VALUE, DOT11_CIPHER_DEFAULT_KEY_VALUE, DOT11_CIPHER_DEFAULT_KEY_VALUE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_dba46983-b572-4b76-8628-776848e4b22e.xml, PDOT11_CIPHER_DEFAULT_KEY_VALUE, PDOT11_CIPHER_DEFAULT_KEY_VALUE structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_cipher_default_key_value, windot11/DOT11_CIPHER_DEFAULT_KEY_VALUE, windot11/PDOT11_CIPHER_DEFAULT_KEY_VALUE"
f1_keywords:
 - "windot11/DOT11_CIPHER_DEFAULT_KEY_VALUE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_CIPHER_DEFAULT_KEY_VALUE
targetos: Windows
req.typenames: DOT11_CIPHER_DEFAULT_KEY_VALUE, *PDOT11_CIPHER_DEFAULT_KEY_VALUE
product:
- Windows 10 or later.
---

# DOT11_CIPHER_DEFAULT_KEY_VALUE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CIPHER_DEFAULT_KEY_VALUE structure defines a default cipher key or per-station default
  cipher key that will be added to or deleted from the key tables on the 802.11 station. For more information
  about these cipher key types, see
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/802-11-cipher-key-types">802.11 Cipher Key Types</a>.


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


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_CIPHER_DEFAULT_KEY_VALUE structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <i>Header</i> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_CIPHER_DEFAULT_KEY_VALUE_REVISION_1.



#### Size

This member must be set to
       <code>sizeof(DOT11_CIPHER_DEFAULT_KEY_VALUE)</code>.

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uKeyIndex

The index of the key in the 802.11 station's default key array.


For standard 802.11 cipher algorithms,
     <b>uKeyIndex</b> must be from 0 through 3. For a cipher algorithm developed by an IHV,
     <b>uKeyIndex</b> can be any value within the range defined by the IHV.

For BIP <b>uKeyIndex</b> must be 4 or 5.

The IEEE 802.11-2012 standard defines default key index values from 1 through 4. The value
     <i>x</i> specified by this member maps to the 802.11 default key index
     (<i>x</i> + 1).


### -field AlgorithmId

The value of the cipher algorithm that uses this key. For more information about values for cipher
     algorithms, see
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>.


For BIP, this should be set to DOT11_CIPHER_ALGO_BIP to pre-set the initial IGTK packet number.

The miniport driver must ignore this member if
     <b>bDelete</b> is <b>TRUE</b>.


### -field MacAddr

The media access control (MAC) address, which identifies the default key table to add or remove
     the key.


If the
     <b>dot11DesiredBSSType</b> management information base (MIB) object is set to
     <b>dot11_BSS_type_infrastructure</b>, the 802.11 station adds or removes the key from the default key
     table regardless of the value of the
     <b>MacAddr</b> member. If the key is dynamically obtained from the access point (AP) the station is
     associated with, the
     <b>MacAddr</b> member will contain the AP's MAC address. Otherwise,
     <b>MacAddr</b> will have a value of 0x000000000000.

If the
     <b>dot11DesiredBSSType</b> management information base (MIB) object is set to
     <b>dot11_BSS_type_independent</b>, the 802.11 station must add or remove the key in the following
     way:

<ul>
<li>
If the value of this member is 0x000000000000, the 802.11 station adds or removes the key from the
       default key table. When the NIC is in the Extensible Access Point (ExtAP) OP mode, this value is
       zero.

</li>
<li>
If the value of this member is a valid unicast MAC address, the 802.11 station adds or removes the
       key from the per-station default key table for the peer station in an independent BSS (IBSS) network
       with a MAC address equal to the value of
       <b>MacAddr</b> .

If a per-station default key table does not exist for the value of
       <b>MacAddr</b>, the 802.11 station must use any unused per-station default key table.

</li>
</ul>

For more information about the <b>dot11DesiredBSSType</b> MIB object, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>.


### -field bDelete

A Boolean value that specifies whether the miniport driver should delete the default key.


If set to <b>TRUE</b>, the miniport driver must delete the default key referenced by
     <b>uKeyIndex</b>. If set to <b>FALSE</b>, the miniport driver must add or update the default key referenced by
     <b>uKeyIndex</b> .


### -field bStatic

A Boolean value that specifies whether the miniport driver should delete the default key following
     a connection or roaming operation.


If set to <b>FALSE</b>, the miniport driver must delete the default key referenced by
     <b>uKeyIndex</b> whenever the 802.11 station:

<ul>
<li>
Disconnects from the basic service set (BSS) network.

</li>
<li>
Roams to a new BSS network.

</li>
<li>
Reconnects to the same BSS network.

</li>
</ul>
If set to <b>TRUE</b>, the default key referenced by
     <b>uKeyIndex</b> must not be deleted unless it is:

<ul>
<li>
Explicitly deleted through a set request of
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">
       OID_DOT11_CIPHER_DEFAULT_KEY</a>.

</li>
<li>
Implicitly deleted through a method request of
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>.

</li>
</ul>

### -field usKeyLength

The length, in bytes, of the key material in the
     <b>ucKey</b> array.


### -field ucKey

The key material.


If
     <b>AlgorithmId</b> is set to
     <b>DOT11_CIPHER_ALGO_TKIP</b>, the
     <b>ucKey</b> array defines the key material through the
     <a href="..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md">
     DOT11_KEY_ALGO_TKIP_MIC</a> structure.

If
     <b>AlgorithmId</b> is set to
     <b>DOT11_CIPHER_ALGO_CCMP</b>, the
     <b>ucKey</b> array defines the key material through the
     <a href="..\windot11\ns-windot11-dot11_key_algo_ccmp.md">
     DOT11_KEY_ALGO_CCMP</a> structure.

If
     <b>AlgorithmId</b> is set to
     <b>DOT11_CIPHER_ALGO_BIP</b>, the
     <b>ucKey</b> array defines the key material through the

     <a href="..\windot11\ns-windot11-dot11_key_algo_bip.md">DOT11_KEY_ALGO_BIP</a> structure.


## -remarks



If the
    <b>bDelete</b> member is <b>TRUE</b>, the following members are not valid and must be ignored:

<ul>
<li>
<b>bStatic</b>

</li>
<li>
<b>usKeyLength</b>

</li>
<li>
<b>ucKey</b>

</li>
</ul>



## -see-also

<a href="..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md">DOT11_KEY_ALGO_TKIP_MIC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>



<a href="..\windot11\ns-windot11-dot11_key_algo_ccmp.md">DOT11_KEY_ALGO_CCMP</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


