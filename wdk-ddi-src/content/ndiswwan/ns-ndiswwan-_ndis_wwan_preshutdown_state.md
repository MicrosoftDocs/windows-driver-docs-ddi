---
UID: NS:ndiswwan._NDIS_WWAN_PRESHUTDOWN_STATE
title: "_NDIS_WWAN_PRESHUTDOWN_STATE"
author: windows-driver-content
description: The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status.
old-location: netvista\ndis_wwan_preshutdown_state.htm
old-project: netvista
ms.assetid: 39653A36-FFED-4F6A-9365-17E9D35DB46E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_WWAN_PRESHUTDOWN_STATE, NDIS_WWAN_PRESHUTDOWN_STATE, NDIS_WWAN_PRESHUTDOWN_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PRESHUTDOWN_STATE, PNDIS_WWAN_PRESHUTDOWN_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_PRESHUTDOWN_STATE, ndiswwan/NDIS_WWAN_PRESHUTDOWN_STATE, ndiswwan/PNDIS_WWAN_PRESHUTDOWN_STATE, netvista.ndis_wwan_preshutdown_state"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 10, version 1511.
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
-	NDIS_WWAN_PRESHUTDOWN_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_PRESHUTDOWN_STATE, *PNDIS_WWAN_PRESHUTDOWN_STATE
---

# _NDIS_WWAN_PRESHUTDOWN_STATE structure


## -description


The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status.


## -syntax


````
typedef struct _NDIS_WWAN_PRESHUTDOWN_STATE {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
} NDIS_WWAN_PRESHUTDOWN_STATE, *PNDIS_WWAN_PRESHUTDOWN_STATE;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PRESHUTDOWN_STATE
     structure. 

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
 NDIS_WWAN_PRESHUTDOWN_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PRESHUTDOWN_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The following table shows the possible status codes.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
Pre-shutdown operations are complete and the host can power down the MBB driver.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The modem does not support pre-shutdown notifications.

</td>
</tr>
</table>
 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt593239">OID_WWAN_PRESHUTDOWN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt593233">NDIS_STATUS_WWAN_PRESHUTDOWN_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PRESHUTDOWN_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

