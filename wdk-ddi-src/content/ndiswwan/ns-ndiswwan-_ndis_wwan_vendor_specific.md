---
UID: NS:ndiswwan._NDIS_WWAN_VENDOR_SPECIFIC
title: _NDIS_WWAN_VENDOR_SPECIFIC (ndiswwan.h)
description: The NDIS_WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.
old-location: netvista\ndis_wwan_vendor_specific.htm
tech.root: netvista
ms.assetid: eaa1f56a-ade6-47d7-8114-8cdb8b015e75
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_VENDOR_SPECIFIC structure"]
ms.keywords: "*PNDIS_WWAN_VENDOR_SPECIFIC, NDIS_WWAN_VENDOR_SPECIFIC, NDIS_WWAN_VENDOR_SPECIFIC structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_VENDOR_SPECIFIC, PNDIS_WWAN_VENDOR_SPECIFIC structure pointer [Network Drivers Starting with Windows Vista], WwanRef_01a97be2-1ce1-484b-b844-654b4171330f.xml, _NDIS_WWAN_VENDOR_SPECIFIC, ndiswwan/NDIS_WWAN_VENDOR_SPECIFIC, ndiswwan/PNDIS_WWAN_VENDOR_SPECIFIC, netvista.ndis_wwan_vendor_specific"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.typenames: NDIS_WWAN_VENDOR_SPECIFIC, *PNDIS_WWAN_VENDOR_SPECIFIC
f1_keywords:
 - _NDIS_WWAN_VENDOR_SPECIFIC
 - ndiswwan/_NDIS_WWAN_VENDOR_SPECIFIC
 - PNDIS_WWAN_VENDOR_SPECIFIC
 - ndiswwan/PNDIS_WWAN_VENDOR_SPECIFIC
 - NDIS_WWAN_VENDOR_SPECIFIC
 - ndiswwan/NDIS_WWAN_VENDOR_SPECIFIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_VENDOR_SPECIFIC
---

# _NDIS_WWAN_VENDOR_SPECIFIC structure


## -description

The NDIS_WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_VENDOR_SPECIFIC
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_VENDOR_SPECIFIC_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_VENDOR_SPECIFIC)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field VendorSpecificData

A formatted 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_vendor_specific">WWAN_VENDOR_SPECIFIC</a> object that
     represents vendor-specific data.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_vendor_specific">WWAN_VENDOR_SPECIFIC</a>