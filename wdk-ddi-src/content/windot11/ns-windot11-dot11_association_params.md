---
UID: NS:windot11.DOT11_ASSOCIATION_PARAMS
title: DOT11_ASSOCIATION_PARAMS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_association_params.htm
tech.root: netvista
ms.assetid: 74382195-ee1d-4b01-b882-2f357d801a25
ms.date: 02/16/2018
keywords: ["DOT11_ASSOCIATION_PARAMS structure"]
ms.keywords: "*PDOT11_ASSOCIATION_PARAMS, DOT11_ASSOCIATION_PARAMS, DOT11_ASSOCIATION_PARAMS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_08a8e9e4-9b11-47f6-a3e0-baa25a63bd6f.xml, PDOT11_ASSOCIATION_PARAMS, PDOT11_ASSOCIATION_PARAMS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_association_params, windot11/DOT11_ASSOCIATION_PARAMS, windot11/PDOT11_ASSOCIATION_PARAMS"
f1_keywords:
 - "windot11/DOT11_ASSOCIATION_PARAMS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
- DOT11_ASSOCIATION_PARAMS
targetos: Windows
req.typenames: DOT11_ASSOCIATION_PARAMS, *PDOT11_ASSOCIATION_PARAMS
product:
- Windows 10 or later.
---

# DOT11_ASSOCIATION_PARAMS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ASSOCIATION_PARAMS structure specifies the list of additional information elements (IEs)
  that the miniport driver appends to the association request that the NIC sends to an access point in an
  infrastructure BSS network.


## -syntax


```cpp
typedef struct DOT11_ASSOCIATION_PARAMS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  BSSID;
  ULONG              uAssocRequestIEsOffset;
  ULONG              uAssocRequestIEsLength;
} DOT11_ASSOCIATION_PARAMS, *PDOT11_ASSOCIATION_PARAMS;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_ASSOCIATION_PARAMS structure. This member is formatted
     as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_ASSOCIATION_PARAMS_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_ASSOCIATION_PARAMS).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field BSSID

The basic service set (BSS) identifier (BSSID) of the infrastructure BSS network for which the
     association parameters are to be set.


The miniport driver should add new additional information elements (IEs) to an association request
     only if it is attempting to associate with an access point that has the matching BSSID.

If this member is set to the wildcard BSSID (0xFFFFFFFFFFFF), the miniport driver should add new
     additional information elements (IEs) to association requests for all access points that have valid
     BSSIDs.


### -field uAssocRequestIEsOffset

The offset of the additional IEs, in bytes, that the operating system requests be added to the
     association response. This offset is relative to the start of the buffer that contains the
     DOT11_ASSOCIATION_PARAMS structure. The default value is 0.


### -field uAssocRequestIEsLength

The length of the additional IEs, in bytes, that the operating system requests be added to the
     association response. The default value is 0.


## -remarks



This structure is used with
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-association-params">OID_DOT11_ASSOCIATION_PARAMS</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-association-params">OID_DOT11_ASSOCIATION_PARAMS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


