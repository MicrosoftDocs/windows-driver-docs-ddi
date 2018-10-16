---
UID: NS:windot11.DOT11_CIPHER_ALGORITHM_LIST
title: DOT11_CIPHER_ALGORITHM_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_algorithm_list.htm
tech.root: netvista
ms.assetid: b6d96a82-f744-4663-8373-886f4245c106
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_704d7a5a-0cf5-459f-af0c-06dfdc936a9e.xml, PDOT11_CIPHER_ALGORITHM_LIST, PDOT11_CIPHER_ALGORITHM_LIST structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_cipher_algorithm_list, windot11/DOT11_CIPHER_ALGORITHM_LIST, windot11/PDOT11_CIPHER_ALGORITHM_LIST"
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
-	DOT11_CIPHER_ALGORITHM_LIST
product:
- Windows
targetos: Windows
req.typenames: DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST
product:
- Windows 10 or later.
---

# DOT11_CIPHER_ALGORITHM_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CIPHER_ALGORITHM_LIST structure defines a list of
  <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> structures that
  can be enabled on the 802.11 station.


## -syntax


```cpp
typedef struct DOT11_CIPHER_ALGORITHM_LIST {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uNumOfEntries;
  ULONG                  uTotalNumOfEntries;
  DOT11_CIPHER_ALGORITHM AlgorithmIds[1];
} DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_CIPHER_ALGORITHM_LIST structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_CIPHER_ALGORITHM_LIST_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_CIPHER_ALGORITHM_LIST).

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
    <a href="https://msdn.microsoft.com/library/gg157261.aspx">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.

When these OIDs are queried, the miniport driver must verify that the
    <b>InformationBuffer</b> member of the
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_CIPHER_ALGORITHM_LIST structure,
    including all entries in the
    <b>AlgorithmIds</b> array. The value of the
    <b>InformationBufferLength</b> member of the
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

<ul>
<li>
If the value of the
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire
      DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following:

<ul>
<li>
For the
        <i>OidRequest</i> parameter, set the
        <b>BytesWritten</b> member to zero and the
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST
        structure.

</li>
<li>
Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

</li>
</ul>
</li>
<li>
If the value of the
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following to complete a
      successful query request:

<ul>
<li>
For the DOT11_CIPHER_ALGORITHM_LIST structure, set the
        <b>uNumOfEntries</b> and
        <b>uTotalNumOfEntries</b> members to the total number of entries in the
        <b>AlgorithmIds</b> array.

</li>
<li>
For the
        <i>OidRequest</i> parameter, set the
        <b>BytesNeeded</b> member to zero and the
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST
        structure. The miniport driver must also copy the entire DOT11_CIPHER_ALGORITHM_LIST structure to the

        <b>InformationBuffer</b> member.

</li>
<li>
Return NDIS_STATUS_SUCCESS from its
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

</li>
</ul>
</li>
</ul>



## -see-also

<a href="https://msdn.microsoft.com/library/gg157261.aspx">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


