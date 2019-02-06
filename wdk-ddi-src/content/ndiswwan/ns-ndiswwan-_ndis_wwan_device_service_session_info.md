---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO
title: _NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure represents the status of a device service session.
old-location: netvista\ndis_wwan_device_service_session_info.htm
tech.root: netvista
ms.assetid: B357E186-FE99-448A-B242-13A21A729BC9
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_SESSION_COMPLETE, NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO, NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_SESSION_INFO, PNDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_SESSION_INFO, netvista.ndis_wwan_device_service_session_info"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_COMPLETE
---

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure represents the status of a device service session.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO
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
NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the device service session state operation.


### -field Session

The session to obtain status of.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831873">WWAN_DEVICE_SERVICE_SESSION</a>
 

 

