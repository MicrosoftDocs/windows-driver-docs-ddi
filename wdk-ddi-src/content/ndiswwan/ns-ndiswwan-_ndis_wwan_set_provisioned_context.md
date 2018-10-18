---
UID: NS:ndiswwan._NDIS_WWAN_SET_PROVISIONED_CONTEXT
title: "_NDIS_WWAN_SET_PROVISIONED_CONTEXT"
author: windows-driver-content
description: The NDIS_WWAN_SET_PROVISIONED_CONTEXT structure represents the command to set the provisioned context state of the MB device.
old-location: netvista\ndis_wwan_set_provisioned_context.htm
tech.root: netvista
ms.assetid: c0f77100-ffd0-4fef-80b0-fc399ef96aee
ms.date: 5/2/2018
ms.keywords: "*PNDIS_WWAN_SET_PROVISIONED_CONTEXT, NDIS_WWAN_SET_PROVISIONED_CONTEXT, NDIS_WWAN_SET_PROVISIONED_CONTEXT structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PROVISIONED_CONTEXT, PNDIS_WWAN_SET_PROVISIONED_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], WwanRef_0f679f5b-26a4-4069-b4d7-65835090f56f.xml, _NDIS_WWAN_SET_PROVISIONED_CONTEXT, ndiswwan/NDIS_WWAN_SET_PROVISIONED_CONTEXT, ndiswwan/PNDIS_WWAN_SET_PROVISIONED_CONTEXT, netvista.ndis_wwan_set_provisioned_context"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SET_PROVISIONED_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PROVISIONED_CONTEXT, *PNDIS_WWAN_SET_PROVISIONED_CONTEXT
---

# _NDIS_WWAN_SET_PROVISIONED_CONTEXT structure


## -description


The NDIS_WWAN_SET_PROVISIONED_CONTEXT structure represents the command to set the provisioned context
  state of the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PROVISIONED_CONTEXT
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
NDIS_WWAN_SET_PROVISIONED_CONTEXT_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PROVISIONED_CONTEXT)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field ProvisionedContext

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571234">WWAN_SET_CONTEXT</a> object that represents a
     provisioned context.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>
 

 

