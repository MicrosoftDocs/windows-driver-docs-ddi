---
UID: NS:ndiswwan._NDIS_WWAN_MAC_PARAMETERS
title: "_NDIS_WWAN_MAC_PARAMETERS"
author: windows-driver-content
description: The NDIS_WWAN_MAC_PARAMETERS structure is used by OID_WWAN_CREATE_MAC when processing a request to create an NDIS port for a new PDP context.
old-location: netvista\ndis_wwan_mac_parameters.htm
old-project: netvista
ms.assetid: 661DA853-E848-4FEB-995F-EC5F20CE36EB
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PNDIS_WWAN_MAC_PARAMETERS, PNDIS_WWAN_MAC_PARAMETERS, NDIS_WWAN_MAC_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_MAC_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_MAC_PARAMETERS, NDIS_WWAN_MAC_PARAMETERS, _NDIS_WWAN_MAC_PARAMETERS, ndiswwan/PNDIS_WWAN_MAC_PARAMETERS, netvista.ndis_wwan_mac_parameters"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
-	NDIS_WWAN_MAC_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_MAC_PARAMETERS, *PNDIS_WWAN_MAC_PARAMETERS
---

# _NDIS_WWAN_MAC_PARAMETERS structure


## -description


The NDIS_WWAN_MAC_PARAMETERS structure is used by <a href="https://msdn.microsoft.com/library/windows/hardware/dn449750">OID_WWAN_CREATE_MAC</a> when processing a request to create an NDIS port for a new PDP context.


## -syntax


````
typedef struct _NDIS_WWAN_MAC_PARAMETERS {
  NDIS_OBJECT_HEADER  Header;
} NDIS_WWAN_MAC_PARAMETERS, *PNDIS_WWAN_MAC_PARAMETERS;
````


## -struct-fields




#### - Header

The header with type, revision, and size information about the NDIS_WWAN_MAC_PARAMETERS structure.
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
NDIS_WWAN_MAC_PARAMETERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_MAC_PARAMETERS)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn449750">OID_WWAN_CREATE_MAC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_MAC_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

