---
UID: NS:ndiswwan._NDIS_WWAN_SLOT_INFO
title: "_NDIS_WWAN_SLOT_INFO"
author: windows-driver-content
description: The NDIS_WWAN_SLOT_INFO structure represents the information about a slot in the modem of the MB device.
old-location: netvista\ndis_wwan_slot_info_status.htm
old-project: netvista
ms.assetid: 21D9DE55-2A26-467A-B119-8AFD4B47A4FD
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_WWAN_SLOT_INFO, NDIS_WWAN_SLOT_INFO, NDIS_WWAN_SLOT_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SLOT_INFO, PNDIS_WWAN_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SLOT_INFO, ndiswwan/NDIS_WWAN_SLOT_INFO, ndiswwan/PNDIS_WWAN_SLOT_INFO, netvista.ndis_wwan_slot_info_status"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
-	NDIS_WWAN_SLOT_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SLOT_INFO, *PNDIS_WWAN_SLOT_INFO
---

# _NDIS_WWAN_SLOT_INFO structure


## -description


The <b>NDIS_WWAN_SLOT_INFO</b> structure represents the information about a slot in the modem of the MB device.


## -syntax


````
typedef struct _NDIS_WWAN_SLOT_INFO {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_SLOT_INFO     SlotInfoStatus;
} NDIS_WWAN_SLOT_INFO, *PNDIS_WWAN_SLOT_INFO;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_SLOT_INFO</b> structure.
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
NDIS_WWAN_SLOT_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SLOT_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of system capability. The following table shows the possible values for
     this member.
     

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
The operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_PARAMETERS

</td>
<td>
The operation failed because of invalid parameters (e.g. slot numbers out of range).

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        when the ready-state is not 
        <b>WwanReadyStateOff</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support this OID.

</td>
</tr>
</table>
 


### -field SlotInfo

 




#### - SlotInfoStatus

A formatted <a href="..\wwan\ns-wwan-_wwan_slot_info.md">WWAN_SLOT_INFO</a> structure which represents the status of a slot in the modem.


## -see-also

<a href="https://msdn.microsoft.com/FA1E16E4-56A3-4401-875F-D75DD01FE75D">NDIS_STATUS_WWAN_SLOT_INFO</a>



<a href="https://msdn.microsoft.com/6267D480-5055-4A7A-B2A0-F4DF9154DCD7">OID_WWAN_SLOT_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_slot_info.md">WWAN_SLOT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SLOT_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

