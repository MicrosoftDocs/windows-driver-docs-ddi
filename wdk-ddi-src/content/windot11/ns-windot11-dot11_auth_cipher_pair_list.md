---
UID: NS:windot11.DOT11_AUTH_CIPHER_PAIR_LIST
title: DOT11_AUTH_CIPHER_PAIR_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_auth_cipher_pair_list.htm
old-project: netvista
ms.assetid: e1440041-a7cd-45c6-8aa5-445d6de2bc20
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_AUTH_CIPHER_PAIR_LIST, DOT11_AUTH_CIPHER_PAIR_LIST, *PDOT11_AUTH_CIPHER_PAIR_LIST
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
req.alt-api: DOT11_AUTH_CIPHER_PAIR_LIST
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
req.typenames: DOT11_AUTH_CIPHER_PAIR_LIST, *PDOT11_AUTH_CIPHER_PAIR_LIST
req.product: Windows 10 or later.
---

# DOT11_AUTH_CIPHER_PAIR_LIST structure



## -description

## -syntax

````
typedef struct DOT11_AUTH_CIPHER_PAIR_LIST {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uNumOfEntries;
  ULONG                  uTotalNumOfEntries;
  DOT11_AUTH_CIPHER_PAIR AuthCipherPairs[1];
} DOT11_AUTH_CIPHER_PAIR_LIST, *PDOT11_AUTH_CIPHER_PAIR_LIST;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_AUTH_CIPHER_PAIR_LIST structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <i>Header</i> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_AUTH_CIPHER_PAIR_LIST_REVISION_1.


### -field Size

This member must be set to 
       <code>sizeof(DOT11_AUTH_CIPHER_PAIR_LIST)</code>.

</dd>
</dl>
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
    <a href="netvista.oid_dot11_supported_unicast_algorithm_pair">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or 
    <a href="netvista.oid_dot11_supported_multicast_algorithm_pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.

When these OIDs are queried, the miniport driver must verify that the 
    <b>InformationBuffer</b> member of the 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_AUTH_CIPHER_PAIR_LIST structure,
    including all entries in the 
    <b>AuthCipherPairs</b> array. The value of the 
    <b>InformationBufferLength</b> member of the 
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

If the value of the 
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire
      DOT11_AUTH_CIPHER_PAIR_LIST structure, the miniport driver must do the following:

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesWritten</b> member to zero and the 
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_AUTH_CIPHER_PAIR_LIST
        structure.

Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

If the value of the 
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_AUTH_CIPHER_PAIR_LIST structure, the miniport driver must do the following to complete a
      successful query request:

For the DOT11_AUTH_CIPHER_PAIR_LIST structure, set the 
        <b>uNumOfEntries</b> and 
        <b>uTotalNumOfEntries</b> members to the total number of entries in the 
        <b>AuthCipherPairs</b> array.

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesNeeded</b> member to zero and the 
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_AUTH_CIPHER_PAIR_LIST
        structure. The miniport driver must also copy the entire DOT11_AUTH_CIPHER_PAIR_LIST structure to the
        
        <b>InformationBuffer</b> member.

Return NDIS_STATUS_SUCCESS from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

Starting with Windows 7, an 802.11 miniport driver can report any combination of supported
    authentication and cipher algorithm pairs in DOT11_AUTH_CIPHER_PAIR_LIST. However, if the operating
    system starts Soft AP, it enables only the 
    <b>DOT11_AUTH_ALGO_RSNA_PSK</b> authentication algorithm and the 
    <b>DOT11_CIPHER_ALGO_CCMP</b> cipher algorithm. To support Soft AP, the miniport driver must support this
    authentication/cipher pair.

If WPS is enabled on a NIC that is operating in Extensible AP mode, the miniport driver must allow
    peer stations to associate with the Extensible AP by using 
    <a href="https://msdn.microsoft.com/f07d2d77-ccaf-4599-b59e-6ea4ecf55e0f">Open System Authentication</a> or 
    <a href="https://msdn.microsoft.com/41dd280b-e54c-4233-8051-45e7b1284d1d">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569436">OID_DOT11_WPS_ENABLED</a>.


## -see-also
<dl>
<dt>
<a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.oid_dot11_supported_multicast_algorithm_pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>
</dt>
<dt>
<a href="netvista.oid_dot11_supported_unicast_algorithm_pair">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_AUTH_CIPHER_PAIR_LIST structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

