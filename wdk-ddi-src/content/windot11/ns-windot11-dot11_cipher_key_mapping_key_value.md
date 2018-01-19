---
UID: NS:windot11.DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
title: DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_key_mapping_key_value.htm
old-project: netvista
ms.assetid: 0ab5239d-422e-483e-a633-4efab47311fc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_CIPHER_KEY_MAPPING_KEY_VALUE, *PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE, DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
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
req.alt-api: DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
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
req.typenames: *PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE, DOT11_CIPHER_KEY_MAPPING_KEY_VALUE
req.product: Windows 10 or later.
---

# DOT11_CIPHER_KEY_MAPPING_KEY_VALUE structure



## -description

## -syntax

````
typedef struct DOT11_CIPHER_KEY_MAPPING_KEY_VALUE {
  DOT11_MAC_ADDRESS      PeerMacAddr;
  DOT11_CIPHER_ALGORITHM AlgorithmId;
  DOT11_DIRECTION        Direction;
  BOOLEAN                bDelete;
  BOOLEAN                bStatic;
  USHORT                 usKeyLength;
  UCHAR                  ucKey[1];
} DOT11_CIPHER_KEY_MAPPING_KEY_VALUE, *PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE;
````


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
       <a href="netvista.oid_dot11_cipher_key_mapping_key">
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
    <a href="netvista.oid_dot11_cipher_key_mapping_key">
    OID_DOT11_CIPHER_KEY_MAPPING_KEY</a> is set, the miniport driver can modify or delete an existing key
    only if the values of the 
    <b>PeerMacAddr</b> and 
    <b>Direction</b> members from the set request match the members of the existing key.

If the 
    <b>bDelete</b> member is <b>TRUE</b>, the following members are not valid and must be ignored:

<b>bStatic</b>

<b>usKeyLength</b>

<b>ucKey</b>


## -see-also
<dl>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_key_algo_ccmp.md">DOT11_KEY_ALGO_CCMP</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md">DOT11_KEY_ALGO_TKIP_MIC</a>
</dt>
<dt>
<a href="netvista.oid_dot11_cipher_key_mapping_key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569142">OID_DOT11_DESIRED_BSS_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CIPHER_KEY_MAPPING_KEY_VALUE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

