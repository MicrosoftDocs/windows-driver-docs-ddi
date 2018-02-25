---
UID: NS:ndiswwan._NDIS_WWAN_SET_CONTEXT_STATE
title: "_NDIS_WWAN_SET_CONTEXT_STATE"
author: windows-driver-content
description: The NDIS_WWAN_SET_CONTEXT_STATE structure represents the command to set the context state of the MB device.
old-location: netvista\ndis_wwan_set_context_state.htm
old-project: netvista
ms.assetid: 8aadbfe0-e925-4c58-9ca0-d07dc40a0ff3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_WWAN_SET_CONTEXT_STATE, ,, A, C, D, E, I, N, NDIS_WWAN_SET_CONTEXT_STATE, NDIS_WWAN_SET_CONTEXT_STATE structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_WWAN_SET_CONTEXT_STATE, PNDIS_WWAN_SET_CONTEXT_STATE structure pointer [Network Drivers Starting with Windows Vista], S, T, W, WwanRef_538105aa-7c75-4c30-96ed-4763cf59575d.xml, X, _, _NDIS_WWAN_SET_CONTEXT_STATE, ndiswwan/NDIS_WWAN_SET_CONTEXT_STATE, ndiswwan/PNDIS_WWAN_SET_CONTEXT_STATE, netvista.ndis_wwan_set_context_state"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_SET_CONTEXT_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_CONTEXT_STATE, *PNDIS_WWAN_SET_CONTEXT_STATE
---

# _NDIS_WWAN_SET_CONTEXT_STATE structure


## -description


The NDIS_WWAN_SET_CONTEXT_STATE structure represents the command to set the context state of the MB
  device.


## -syntax


````
typedef struct _NDIS_WWAN_SET_CONTEXT_STATE {
  NDIS_OBJECT_HEADER     Header;
  WWAN_SET_CONTEXT_STATE SetContextState;
} NDIS_WWAN_SET_CONTEXT_STATE, *PNDIS_WWAN_SET_CONTEXT_STATE;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_CONTEXT_STATE
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
NDIS_WWAN_SET_CONTEXT_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_CONTEXT_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field SetContextState

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a> object that
     represents the command to set the Packet Data Protocol (PDP) context state of the MB device.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_CONTEXT_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

