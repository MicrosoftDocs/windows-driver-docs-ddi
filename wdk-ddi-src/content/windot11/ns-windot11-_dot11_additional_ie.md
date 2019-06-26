---
UID: NS:windot11._DOT11_ADDITIONAL_IE
title: _DOT11_ADDITIONAL_IE (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_additional_ie.htm
tech.root: netvista
ms.assetid: db034863-f5fa-42bb-81c8-23d4784e0abe
ms.date: 02/16/2018
ms.keywords: "*PDOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_306f816b-e8fa-4f61-be10-5fd4d793f5a5.xml, PDOT11_ADDITIONAL_IE, PDOT11_ADDITIONAL_IE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_ADDITIONAL_IE, netvista.dot11_additional_ie, windot11/DOT11_ADDITIONAL_IE, windot11/PDOT11_ADDITIONAL_IE"
ms.topic: struct
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
- DOT11_ADDITIONAL_IE
product:
- Windows
targetos: Windows
req.typenames: DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE
product:
- Windows 10 or later.
---

# _DOT11_ADDITIONAL_IE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_ADDITIONAL_IE structure specifies characteristics of additional information elements (IEs)
  for a BSS 802.11 Beacon or Probe Response frame.


## -syntax


```cpp
typedef struct _DOT11_ADDITIONAL_IE {
  NDIS_OBJECT_HEADER Header;
  ULONG              uBeaconIEsOffset;
  ULONG              uBeaconIEsLength;
  ULONG              uResponseIEsOffset;
  ULONG              uResponseIEsLength;
} DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_ADDITIONAL_IE structure. This member is formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_ADDITIONAL_IE_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_ADDITIONAL_IE).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uBeaconIEsOffset

The offset of the additional IEs, in bytes, in the beacon frame sent by the NIC. This offset is
     relative to the start of the buffer that contains the DOT11_ADDITIONAL_IE structure. The default value
     is 0.


### -field uBeaconIEsLength

The length of the additional IEs, in bytes, in the beacon frame sent by the NIC. The default value
     is 0.


### -field uResponseIEsOffset

The offset of the additional IEs, in bytes, in the probe response frame sent by the NIC. This
     offset is relative to the start of the buffer that contains the DOT11_ADDITIONAL_IE structure. The
     default value is 0.


### -field uResponseIEsLength

The length of the additional IEs, in bytes, in the probe response frame sent by the NIC. The
     default value is 0.


## -remarks



This structure is used with
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-additional-ie">OID_DOT11_ADDITIONAL_IE</a>.

The miniport driver should reset the members of the DOT11_ADDITIONAL_IE structure to the default
    values when it receives an
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a> request.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-additional-ie">OID_DOT11_ADDITIONAL_IE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


