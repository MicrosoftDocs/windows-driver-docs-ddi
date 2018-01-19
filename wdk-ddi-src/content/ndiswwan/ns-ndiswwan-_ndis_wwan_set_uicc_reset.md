---
UID: NS:ndiswwan._NDIS_WWAN_SET_UICC_RESET
title: _NDIS_WWAN_SET_UICC_RESET
author: windows-driver-content
description: The NDIS_WWAN_SET_UICC_RESET structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC card.
old-location: netvista\ndis_wwan_set_uicc_reset.htm
old-project: netvista
ms.assetid: 98113BC2-317C-4FBD-B3A6-A14B3783D225
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_SET_UICC_RESET, *PNDIS_WWAN_SET_UICC_RESET, NDIS_WWAN_SET_UICC_RESET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_SET_UICC_RESET
req.alt-loc: ndiswwan.h
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
req.typenames: *PNDIS_WWAN_SET_UICC_RESET, NDIS_WWAN_SET_UICC_RESET
---

# _NDIS_WWAN_SET_UICC_RESET structure



## -description
The <b>NDIS_WWAN_SET_UICC_RESET</b> structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC card.



## -syntax

````
typedef struct _NDIS_WWAN_SET_UICC_RESET {
  NDIS_OBJECT_HEADER  Header;
  WWAN_SET_UICC_RESET SetUiccReset;
} NDIS_WWAN_SET_UICC_RESET, *PNDIS_WWAN_SET_UICC_RESET;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field SetUiccReset

A formatted <a href="..\wwan\ns-wwan-_wwan_set_uicc_reset.md">WWAN_SET_UICC_RESET</a> structure that represents the passthrough action the host specifies for the miniport adapter after it resets the UICC.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_set_uicc_reset.md">WWAN_SET_UICC_RESET</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-reset">OID_WWAN_UICC_RESET</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_UICC_RESET structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

