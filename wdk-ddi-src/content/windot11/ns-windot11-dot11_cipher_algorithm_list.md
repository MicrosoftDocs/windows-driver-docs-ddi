---
UID: NS:windot11.DOT11_CIPHER_ALGORITHM_LIST
title: DOT11_CIPHER_ALGORITHM_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_algorithm_list.htm
old-project: netvista
ms.assetid: b6d96a82-f744-4663-8373-886f4245c106
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_CIPHER_ALGORITHM_LIST
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
req.typenames: *PDOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST
req.product: Windows 10 or later.
---

# DOT11_CIPHER_ALGORITHM_LIST structure



## -description

## -syntax

````
typedef struct DOT11_CIPHER_ALGORITHM_LIST {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uNumOfEntries;
  ULONG                  uTotalNumOfEntries;
  DOT11_CIPHER_ALGORITHM AlgorithmIds[1];
} DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_CIPHER_ALGORITHM_LIST structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_CIPHER_ALGORITHM_LIST_REVISION_1.


### -field Size

This member must be set to 
       sizeof(DOT11_CIPHER_ALGORITHM_LIST).

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumOfEntries

The number of entries in the 
     <b>AlgorithmIds</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the 
     <b>AlgorithmIds</b> array can contain.


### -field AlgorithmIds

The cipher algorithm, which is defined by a 
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> enumerator
     value.
     

The list of cipher algorithms is sorted by preference. 
     <b>AlgorithmIds</b> [0] defines the cipher algorithm with the highest preference.


## -remarks
A miniport driver returns the DOT11_CIPHER_ALGORITHM_LIST structure when it is queried by either 
    <a href="netvista.oid_dot11_supported_unicast_algorithm_pair">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or 
    <a href="netvista.oid_dot11_supported_multicast_algorithm_pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.

When these OIDs are queried, the miniport driver must verify that the 
    <b>InformationBuffer</b> member of the 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_CIPHER_ALGORITHM_LIST structure,
    including all entries in the 
    <b>AlgorithmIds</b> array. The value of the 
    <b>InformationBufferLength</b> member of the 
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

If the value of the 
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire
      DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following:

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesWritten</b> member to zero and the 
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST
        structure.

Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

If the value of the 
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following to complete a
      successful query request:

For the DOT11_CIPHER_ALGORITHM_LIST structure, set the 
        <b>uNumOfEntries</b> and 
        <b>uTotalNumOfEntries</b> members to the total number of entries in the 
        <b>AlgorithmIds</b> array.

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesNeeded</b> member to zero and the 
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST
        structure. The miniport driver must also copy the entire DOT11_CIPHER_ALGORITHM_LIST structure to the
        
        <b>InformationBuffer</b> member.

Return NDIS_STATUS_SUCCESS from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CIPHER_ALGORITHM_LIST structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

