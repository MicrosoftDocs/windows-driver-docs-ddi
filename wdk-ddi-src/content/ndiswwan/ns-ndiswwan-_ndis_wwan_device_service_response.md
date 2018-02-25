---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_RESPONSE
title: "_NDIS_WWAN_DEVICE_SERVICE_RESPONSE"
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure represents device service data from the transaction completion of a device service command.
old-location: netvista\ndis_wwan_device_service_response.htm
old-project: netvista
ms.assetid: 65999499-C14C-45CC-B7A5-021750B1A728
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_WWAN_DEVICE_SERVICE_RESPONSE, ,, A, C, D, E, I, N, NDIS_WWAN_DEVICE_SERVICE_RESPONSE, NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_WWAN_DEVICE_SERVICE_RESPONSE, PNDIS_WWAN_DEVICE_SERVICE_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], R, S, V, W, _, _NDIS_WWAN_DEVICE_SERVICE_RESPONSE, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_RESPONSE, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_RESPONSE, netvista.ndis_wwan_device_service_response"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
-	NDIS_WWAN_DEVICE_SERVICE_RESPONSE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_RESPONSE, *PNDIS_WWAN_DEVICE_SERVICE_RESPONSE
---

# _NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure represents device service data from the transaction completion of a device service command.


## -syntax


````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_RESPONSE {
  NDIS_OBJECT_HEADER           Header;
  WWAN_STATUS                  uStatus;
  WWAN_DEVICE_SERVICE_RESPONSE ResponseData;
} NDIS_WWAN_DEVICE_SERVICE_RESPONSE, *PNDIS_WWAN_DEVICE_SERVICE_RESPONSE;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
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
NDIS_WWAN_DEVICE_SERVICE_RESPONSE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_RESPONSE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the completion of the command.


### -field Response

 




#### - ResponseData

The response from the completion of the device service command.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_device_service_response.md">WWAN_DEVICE_SERVICE_RESPONSE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

