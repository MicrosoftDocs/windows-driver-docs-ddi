---
UID: NS:ndiswwan._NDIS_WWAN_VENDOR_SPECIFIC
title: "_NDIS_WWAN_VENDOR_SPECIFIC"
author: windows-driver-content
description: The NDIS_WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.
old-location: netvista\ndis_wwan_vendor_specific.htm
old-project: netvista
ms.assetid: eaa1f56a-ade6-47d7-8114-8cdb8b015e75
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_WWAN_VENDOR_SPECIFIC, NDIS_WWAN_VENDOR_SPECIFIC, NDIS_WWAN_VENDOR_SPECIFIC structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_VENDOR_SPECIFIC, PNDIS_WWAN_VENDOR_SPECIFIC structure pointer [Network Drivers Starting with Windows Vista], WwanRef_01a97be2-1ce1-484b-b844-654b4171330f.xml, _NDIS_WWAN_VENDOR_SPECIFIC, ndiswwan/NDIS_WWAN_VENDOR_SPECIFIC, ndiswwan/PNDIS_WWAN_VENDOR_SPECIFIC, netvista.ndis_wwan_vendor_specific"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_VENDOR_SPECIFIC
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VENDOR_SPECIFIC, *PNDIS_WWAN_VENDOR_SPECIFIC
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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field VendorSpecificData

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571255">WWAN_VENDOR_SPECIFIC</a> object that
     represents vendor-specific data.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571255">WWAN_VENDOR_SPECIFIC</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_VENDOR_SPECIFIC structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

