---
UID: NS:windot11.DOT11_DISASSOCIATION_PARAMETERS
title: DOT11_DISASSOCIATION_PARAMETERS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_disassociation_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_DISASSOCIATION_PARAMETERS structure"]
ms.keywords: "*PDOT11_DISASSOCIATION_PARAMETERS, DOT11_DISASSOCIATION_PARAMETERS, DOT11_DISASSOCIATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_289b81c2-13d2-484b-9306-6ca3dc961675.xml, PDOT11_DISASSOCIATION_PARAMETERS, PDOT11_DISASSOCIATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_disassociation_parameters, windot11/DOT11_DISASSOCIATION_PARAMETERS, windot11/PDOT11_DISASSOCIATION_PARAMETERS"
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
targetos: Windows
req.typenames: DOT11_DISASSOCIATION_PARAMETERS, *PDOT11_DISASSOCIATION_PARAMETERS
f1_keywords:
 - DOT11_DISASSOCIATION_PARAMETERS
 - windot11/DOT11_DISASSOCIATION_PARAMETERS
 - PDOT11_DISASSOCIATION_PARAMETERS
 - windot11/PDOT11_DISASSOCIATION_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_DISASSOCIATION_PARAMETERS
 - PDOT11_DISASSOCIATION_PARAMETERS
product:
 - Windows 10 or later.
---

# DOT11_DISASSOCIATION_PARAMETERS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DISASSOCIATION_PARAMETERS structure specifies the results of the disassociation operation
  performed by the 802.11 station with either an access point (AP) or peer station. The Native 802.11
  miniport driver includes a DOT11_ASSOCIATION_DISASSOCIATION_PARAMETERS structure when the driver makes an
  <a href="/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
  NDIS_STATUS_DOT11_DISASSOCIATION</a> status indication.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_DISASSOCIATION_PARAMETERS structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_DISASSOCIATION_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_DISASSOCIATION_PARAMETERS).

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field MacAddr

The media access control (MAC) address of the AP or peer station that the 802.11 station has
     disassociated from.


If the miniport driver sets
     <b>MacAddr</b> to the wildcard value of 0xFFFFFFFFFFFF, the 802.11 station has disassociated from the AP
     or all peer stations.

### -field uReason

The reason for the disassociation formatted as a
     <a href="/windows-hardware/drivers/network/dot11-assoc-status-status-codes">DOT11_ASSOC_STATUS</a> value.

### -field uIHVDataOffset

The offset of a block of data in a proprietary format that is defined by the IHV. The IHV can use
      this data block for any purposes that are related to the
      <a href="/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
      NDIS_STATUS_DOT11_DISASSOCIATION</a> status indication.

This offset is relative to the start of the buffer, which contains the
      DOT11_DISASSOCIATION_PARAMETERS structure.

If the miniport driver is not returning IHV data in the
      NDIS_STATUS_DOT11_DISASSOCIATION indication, it must set uIHVDataOffset to
      zero.

### -field uIHVDataSize

The length of the block of data that is used by the IHV for the
     <a href="/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
     NDIS_STATUS_DOT11_DISASSOCIATION</a> status indication. If the miniport driver is not returning IHV
     data in this indication, it must set
     <b>uIHVDataSize</b> to zero.

## -syntax

```cpp
typedef struct DOT11_DISASSOCIATION_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  MacAddr;
  DOT11_ASSOC_STATUS uReason;
  ULONG              uIHVDataOffset;
  ULONG              uIHVDataSize;
} DOT11_DISASSOCIATION_PARAMETERS, *PDOT11_DISASSOCIATION_PARAMETERS;
```

## -remarks

For more information about the disassociation operation, see
    <a href="/windows-hardware/drivers/network/disassociation-operations">Disassociation Operations</a>.

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-dot11-disassociation">
   NDIS_STATUS_DOT11_DISASSOCIATION</a>



<a href="/windows-hardware/drivers/network/dot11-assoc-status-status-codes">DOT11_ASSOC_STATUS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

