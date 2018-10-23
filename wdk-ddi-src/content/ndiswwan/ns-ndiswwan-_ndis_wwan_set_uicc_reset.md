---
UID: NS:ndiswwan._NDIS_WWAN_SET_UICC_RESET
title: "_NDIS_WWAN_SET_UICC_RESET"
author: windows-driver-content
description: The NDIS_WWAN_SET_UICC_RESET structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC card.
old-location: netvista\ndis_wwan_set_uicc_reset.htm
tech.root: netvista
ms.assetid: 98113BC2-317C-4FBD-B3A6-A14B3783D225
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_UICC_RESET, NDIS_WWAN_SET_UICC_RESET, NDIS_WWAN_SET_UICC_RESET structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_UICC_RESET, PNDIS_WWAN_SET_UICC_RESET structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_UICC_RESET, ndiswwan/NDIS_WWAN_SET_UICC_RESET, ndiswwan/PNDIS_WWAN_SET_UICC_RESET, netvista.ndis_wwan_set_uicc_reset"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	NDIS_WWAN_SET_UICC_RESET
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_UICC_RESET, *PNDIS_WWAN_SET_UICC_RESET
---

# _NDIS_WWAN_SET_UICC_RESET structure


## -description


The <b>NDIS_WWAN_SET_UICC_RESET</b> structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC card.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_SET_UICC_RESET</b> structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
NDIS_WWAN_SET_UICC_RESET_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_UICC_RESET)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field SetUiccReset

A formatted <a href="https://msdn.microsoft.com/33711459-70C8-43D2-974D-B90EC0DD8ED6">WWAN_SET_UICC_RESET</a> structure that represents the passthrough action the host specifies for the miniport adapter after it resets the UICC.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-reset">OID_WWAN_UICC_RESET</a>



<a href="https://msdn.microsoft.com/33711459-70C8-43D2-974D-B90EC0DD8ED6">WWAN_SET_UICC_RESET</a>
 

 

