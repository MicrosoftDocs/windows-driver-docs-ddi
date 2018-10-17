---
UID: NS:windot11.DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
title: DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_key_mapping_key_value.htm
tech.root: netvista
ms.assetid: 0ab5239d-422e-483e-a633-4efab47311fc
ms.date: 2/16/2018
ms.keywords: "*PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE, DOT11_CIPHER_KEY_MAPPING_KEY_VALUE, DOT11_CIPHER_KEY_MAPPING_KEY_VALUE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_3be84a7b-4b5b-49d1-8611-3217962483fe.xml, PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE, PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_cipher_key_mapping_key_value, windot11/DOT11_CIPHER_KEY_MAPPING_KEY_VALUE, windot11/PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE"
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
-	DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
product:
- Windows
targetos: Windows
req.typenames: DOT11_CIPHER_KEY_MAPPING_KEY_VALUE, *PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE
product:
- Windows 10 or later.
---

# DOT11_CIPHER_KEY_MAPPING_KEY_VALUE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CIPHER_KEY_MAPPING_KEY_VALUE structure defines a key-mapping cipher key that will be added
  to or deleted from the key tables on the 802.11 station. For more information about this cipher key type,
  see
  <a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>.


## -syntax


```
typedef struct DOT11_CIPHER_KEY_MAPPING_KEY_VALUE {
  DOT11_MAC_ADDRESS      PeerMacAddr;
  DOT11_CIPHER_ALGORITHM AlgorithmId;
  DOT11_DIRECTION        Direction;
  BOOLEAN                bDelete;
  BOOLEAN                bStatic;
  USHORT                 usKeyLength;
  UCHAR                  ucKey[1];
} DOT11_CIPHER_KEY_MAPPING_KEY_VALUE, *PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE;
```


## -struct-fields




### -field PeerMacAddr

MAC address of the peer. The peer is either an access point (AP) (for infrastructure BSS networks)
     or peer station (for independent BSS networks) with which the 802.11 station is associated.


This member is used to uniquely identify a key entry. For the standard 802.11 cipher algorithms, the
     operating system will identify the peer through peer's MAC address. For proprietary cipher algorithms
     developed by an independent hardware vendor (IHV), the IHV can use any method to identify a key
     entry.

When the NIC is in the Extensible Access Point (ExtAP) OP mode,
     <b>PeerMacAddr</b> must have a unique value.


### -field AlgorithmId

The value of the cipher algorithm that uses this key. For more information about enumerator values
     for cipher algorithms, see
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>.


### -field Direction

This member specifies whether the 802.11 station uses the key for receive or transmit packets. The
     data type for this member is the
     <a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a> enumeration.


### -field bDelete

If set to <b>TRUE</b>, the miniport driver must delete the key referenced by
     <b>PeerMacAddr</b> and
     <b>Direction</b> . If set to <b>FALSE</b>, the miniport driver must add or update the key referenced by
     <b>PeerMacAddr</b> and
     <b>Direction</b> .


### -field bStatic

A Boolean value that specifies whether the miniport driver should delete the default key following
     a connection or roaming operation.


If set to <b>FALSE</b>, the miniport driver must delete the default key referenced by
     <b>uKeyIndex</b> whenever:

<ul>
<li>
The 802.11 station disconnects from the BSS network.

</li>
<li>
The peer station disconnects from the BSS network.

</li>
<li>
The 802.11 station reconnects to the same BSS network.

</li>
</ul>
If set to <b>TRUE</b>, the default key referenced by
     <b>uKeyIndex</b> must not be deleted unless it is:

<ul>
<li>
Explicitly deleted through a set request of
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
       OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>.

</li>
<li>
Implicitly deleted through a method request of
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>.

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


## -remarks



The Native 802.11 miniport driver uniquely identifies key-mapping keys through the
    <b>PeerMacAddr</b> and
    <b>Direction</b> members. When the
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
    OID_DOT11_CIPHER_KEY_MAPPING_KEY</a> is set, the miniport driver can modify or delete an existing key
    only if the values of the
    <b>PeerMacAddr</b> and
    <b>Direction</b> members from the set request match the members of the existing key.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md">DOT11_KEY_ALGO_TKIP_MIC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>



<a href="..\windot11\ns-windot11-dot11_key_algo_ccmp.md">DOT11_KEY_ALGO_CCMP</a>



<a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a>



 

 


