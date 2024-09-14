---
UID: NS:windot11._DOT11_ADDITIONAL_IE
title: _DOT11_ADDITIONAL_IE (windot11.h)
description: The DOT11_ADDITIONAL_IE structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_additional_ie.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_ADDITIONAL_IE structure"]
ms.keywords: "*PDOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE, DOT11_ADDITIONAL_IE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_306f816b-e8fa-4f61-be10-5fd4d793f5a5.xml, PDOT11_ADDITIONAL_IE, PDOT11_ADDITIONAL_IE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_ADDITIONAL_IE, netvista.dot11_additional_ie, windot11/DOT11_ADDITIONAL_IE, windot11/PDOT11_ADDITIONAL_IE"
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
targetos: Windows
req.typenames: DOT11_ADDITIONAL_IE, *PDOT11_ADDITIONAL_IE
f1_keywords:
 - _DOT11_ADDITIONAL_IE
 - windot11/_DOT11_ADDITIONAL_IE
 - PDOT11_ADDITIONAL_IE
 - windot11/PDOT11_ADDITIONAL_IE
 - DOT11_ADDITIONAL_IE
 - windot11/DOT11_ADDITIONAL_IE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_ADDITIONAL_IE
 - PDOT11_ADDITIONAL_IE
 - DOT11_ADDITIONAL_IE
---

# _DOT11_ADDITIONAL_IE structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_ADDITIONAL_IE structure specifies characteristics of additional information elements (IEs)
  for a BSS 802.11 Beacon or Probe Response frame.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_ADDITIONAL_IE structure. This member is formatted as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


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
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

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

## -remarks

This structure is used with
    <a href="/windows-hardware/drivers/network/oid-dot11-additional-ie">OID_DOT11_ADDITIONAL_IE</a>.

The miniport driver should reset the members of the DOT11_ADDITIONAL_IE structure to the default
    values when it receives an
    <a href="/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a> request.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-reset-request">OID_DOT11_RESET_REQUEST</a>



<a href="/windows-hardware/drivers/network/oid-dot11-additional-ie">OID_DOT11_ADDITIONAL_IE</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>

