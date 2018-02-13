---
UID: NS:windot11.DOT11_CIPHER_DEFAULT_KEY_VALUE
title: DOT11_CIPHER_DEFAULT_KEY_VALUE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_default_key_value.htm
old-project: netvista
ms.assetid: 7362b20a-6ec4-4b22-8981-3a4b647a3cfa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Native_802.11_data_types_dba46983-b572-4b76-8628-776848e4b22e.xml, netvista.dot11_cipher_default_key_value, DOT11_CIPHER_DEFAULT_KEY_VALUE, windot11/DOT11_CIPHER_DEFAULT_KEY_VALUE, PDOT11_CIPHER_DEFAULT_KEY_VALUE, *PDOT11_CIPHER_DEFAULT_KEY_VALUE, DOT11_CIPHER_DEFAULT_KEY_VALUE structure [Network Drivers Starting with Windows Vista], PDOT11_CIPHER_DEFAULT_KEY_VALUE structure pointer [Network Drivers Starting with Windows Vista], windot11/PDOT11_CIPHER_DEFAULT_KEY_VALUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_CIPHER_DEFAULT_KEY_VALUE
product: Windows
targetos: Windows
req.typenames: "*PDOT11_CIPHER_DEFAULT_KEY_VALUE, DOT11_CIPHER_DEFAULT_KEY_VALUE"
req.product: Windows 10 or later.
---

# DOT11_CIPHER_DEFAULT_KEY_VALUE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CIPHER_DEFAULT_KEY_VALUE structure defines a default cipher key or per-station default
  cipher key that will be added to or deleted from the key tables on the 802.11 station. For more information
  about these cipher key types, see 
  <a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>.


## -syntax


````
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
````


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
For more information about the 
     <b>dot11DesiredBSSType</b> MIB object, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-desired-bss-type">
     OID_DOT11_DESIRED_BSS_TYPE</a>.


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
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">
       OID_DOT11_CIPHER_DEFAULT_KEY</a>.

</li>
<li>
Implicitly deleted through a method request of 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>.

</li>
</ul>

### -field usKeyLength

The length, in bytes, of the key material in the 
     <b>ucKey</b> array.


### -field ucKey.unique

 


### -field ucKey.size_is

 


### -field ucKey.size_is.usKeyLength

 


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

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>



<a href="..\windot11\ns-windot11-dot11_key_algo_ccmp.md">DOT11_KEY_ALGO_CCMP</a>



<a href="..\windot11\ns-windot11-dot11_key_algo_tkip_mic.md">DOT11_KEY_ALGO_TKIP_MIC</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CIPHER_DEFAULT_KEY_VALUE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

