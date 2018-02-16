---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_RESET_STATUS
title: "_NDIS_WWAN_DEVICE_RESET_STATUS"
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_RESET_STATUS structure represents a modem device's reset status. It is sent to the MB host in the NDIS_STATUS_WWAN_DEVICE_RESET_STATUS notification in an asynchronous response to an OID_WWAN_DEVICE_RESET set request.
old-location: netvista\ndis_wwan_device_reset_status.htm
old-project: netvista
ms.assetid: D18E8633-BEAD-49A5-A730-10564AFF8A3E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_WWAN_DEVICE_RESET_STATUS, PNDIS_WWAN_DEVICE_RESET_STATUS structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/PNDIS_WWAN_DEVICE_RESET_STATUS, *PNDIS_WWAN_DEVICE_RESET_STATUS, netvista.ndis_wwan_device_reset_status, ndiswwan/NDIS_WWAN_DEVICE_RESET_STATUS, PNDIS_WWAN_DEVICE_RESET_STATUS, _NDIS_WWAN_DEVICE_RESET_STATUS, NDIS_WWAN_DEVICE_RESET_STATUS structure [Network Drivers Starting with Windows Vista]
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
-	NDIS_WWAN_DEVICE_RESET_STATUS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_RESET_STATUS, *PNDIS_WWAN_DEVICE_RESET_STATUS
---

# _NDIS_WWAN_DEVICE_RESET_STATUS structure


## -description


The <b>NDIS_WWAN_DEVICE_RESET_STATUS</b>  structure represents a modem device's reset status. It is sent to the MB host in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-device-reset-status">NDIS_STATUS_WWAN_DEVICE_RESET_STATUS</a> notification in an asynchronous response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-reset">OID_WWAN_DEVICE_RESET</a> set request.


## -syntax


````
typedef struct _NDIS_WWAN_DEVICE_RESET_STATUS {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
} NDIS_WWAN_DEVICE_RESET_STATUS, *PNDIS_WWAN_DEVICE_RESET_STATUS;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_DEVICE_RESET_STATUS</b> structure.
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
NDIS_WWAN_DEVICE_RESET_STATUS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_RESET_STATUS)

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
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support this OID.

</td>
</tr>
</table>
 


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-modem-reset-operations">MB modem reset operations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-reset">OID_WWAN_DEVICE_RESET</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-device-reset-status">NDIS_STATUS_WWAN_DEVICE_RESET_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_RESET_STATUS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

