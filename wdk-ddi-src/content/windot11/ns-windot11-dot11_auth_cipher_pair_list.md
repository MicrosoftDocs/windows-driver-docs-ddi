---
UID: NS:windot11.DOT11_AUTH_CIPHER_PAIR_LIST
title: DOT11_AUTH_CIPHER_PAIR_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_auth_cipher_pair_list.htm
tech.root: netvista
ms.assetid: e1440041-a7cd-45c6-8aa5-445d6de2bc20
ms.date: 02/16/2018
ms.keywords: "*PDOT11_AUTH_CIPHER_PAIR_LIST, DOT11_AUTH_CIPHER_PAIR_LIST, DOT11_AUTH_CIPHER_PAIR_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_22a0193d-4747-47ac-84dc-067bb30e22ca.xml, PDOT11_AUTH_CIPHER_PAIR_LIST, PDOT11_AUTH_CIPHER_PAIR_LIST structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_auth_cipher_pair_list, windot11/DOT11_AUTH_CIPHER_PAIR_LIST, windot11/PDOT11_AUTH_CIPHER_PAIR_LIST"
f1_keywords:
 - "windot11/DOT11_AUTH_CIPHER_PAIR_LIST"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_AUTH_CIPHER_PAIR_LIST
targetos: Windows
req.typenames: DOT11_AUTH_CIPHER_PAIR_LIST, *PDOT11_AUTH_CIPHER_PAIR_LIST
product:
- Windows 10 or later.
---

# DOT11_AUTH_CIPHER_PAIR_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_AUTH_CIPHER_PAIR_LIST structure defines a list of DOT11_AUTH_CIPHER_PAIR structures.


## -syntax


```cpp
typedef struct DOT11_AUTH_CIPHER_PAIR_LIST {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uNumOfEntries;
  ULONG                  uTotalNumOfEntries;
  DOT11_AUTH_CIPHER_PAIR AuthCipherPairs[1];
} DOT11_AUTH_CIPHER_PAIR_LIST, *PDOT11_AUTH_CIPHER_PAIR_LIST;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_AUTH_CIPHER_PAIR_LIST structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <i>Header</i> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_AUTH_CIPHER_PAIR_LIST_REVISION_1.



#### Size

This member must be set to
       <code>sizeof(DOT11_AUTH_CIPHER_PAIR_LIST)</code>.

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumOfEntries

The number of entries in the
     <b>AuthCipherPairs</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>AuthCipherPairs</b> array can contain.


### -field AuthCipherPairs

The list of
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structures.


## -remarks



A miniport driver returns the DOT11_AUTH_CIPHER_PAIR_LIST structure when queried by either
    <a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg157261(v=winembedded.80)">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.

When these OIDs are queried, the miniport driver must verify that the
    <b>InformationBuffer</b> member of the
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_AUTH_CIPHER_PAIR_LIST structure,
    including all entries in the
    <b>AuthCipherPairs</b> array. The value of the
    <b>InformationBufferLength</b> member of the
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

<ul>
<li>
If the value of the <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire DOT11_AUTH_CIPHER_PAIR_LIST structure, the miniport driver must do the following:
<ul>
<li>
For the <i>OidRequest</i> parameter, set the <b>BytesWritten</b> member to zero and the <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_AUTH_CIPHER_PAIR_LIST structure.

</li>
<li>
Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

</li>
</ul>
</li>
<li>
If the value of the <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire DOT11_AUTH_CIPHER_PAIR_LIST structure, the miniport driver must do the following to complete a successful query request:
<ul>
<li>
For the DOT11_AUTH_CIPHER_PAIR_LIST structure, set the <b>uNumOfEntries</b> and <b>uTotalNumOfEntries</b> members to the total number of entries in the <b>AuthCipherPairs</b> array.
</li>
<li>
For the <i>OidRequest</i> parameter, set the <b>BytesNeeded</b> member to zero and the <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_AUTH_CIPHER_PAIR_LIST structure. The miniport driver must also copy the entire DOT11_AUTH_CIPHER_PAIR_LIST structure to the <b>InformationBuffer</b> member.
</li>
<li>
Return NDIS_STATUS_SUCCESS from its <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.
</li>
</ul>
</li>
</ul>
Starting with Windows 7, an 802.11 miniport driver can report any combination of supported
    authentication and cipher algorithm pairs in DOT11_AUTH_CIPHER_PAIR_LIST. However, if the operating
    system starts Soft AP, it enables only the
    <b>DOT11_AUTH_ALGO_RSNA_PSK</b> authentication algorithm and the
    <b>DOT11_CIPHER_ALGO_CCMP</b> cipher algorithm. To support Soft AP, the miniport driver must support this
    authentication/cipher pair.

If WPS is enabled on a NIC that is operating in Extensible AP mode, the miniport driver must allow
    peer stations to associate with the Extensible AP by using
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/open-system-authentication">Open System Authentication</a> or
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565846(v=vs.85)">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wps-enabled">OID_DOT11_WPS_ENABLED</a>.




## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg157261(v=winembedded.80)">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>



<a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


