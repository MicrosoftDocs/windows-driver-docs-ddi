---
UID: NS:ndiswwan._NDIS_WWAN_SERVICE_ACTIVATION_STATUS
title: _NDIS_WWAN_SERVICE_ACTIVATION_STATUS (ndiswwan.h)
description: The NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the MB device.
old-location: netvista\ndis_wwan_service_activation_status.htm
tech.root: netvista
ms.assetid: 669ef35f-0e59-4ec3-b6cc-5cb2156b51a2
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SERVICE_ACTIVATION_STATUS, NDIS_WWAN_SERVICE_ACTIVATION_STATUS, NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SERVICE_ACTIVATION_STATUS, PNDIS_WWAN_SERVICE_ACTIVATION_STATUS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_a1bda142-c89f-4323-a114-0c44948f61b5.xml, _NDIS_WWAN_SERVICE_ACTIVATION_STATUS, ndiswwan/NDIS_WWAN_SERVICE_ACTIVATION_STATUS, ndiswwan/PNDIS_WWAN_SERVICE_ACTIVATION_STATUS, netvista.ndis_wwan_service_activation_status"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SERVICE_ACTIVATION_STATUS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndiswwan.h
api_name:
- NDIS_WWAN_SERVICE_ACTIVATION_STATUS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SERVICE_ACTIVATION_STATUS, *PNDIS_WWAN_SERVICE_ACTIVATION_STATUS
---

# _NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure


## -description


The NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the
  MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SERVICE_ACTIVATION_STATUS
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
NDIS_WWAN_SERVICE_ACTIVATION_STATUS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SERVICE_ACTIVATION_STATUS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the service activation operation. The following table shows the possible values for
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
Service activation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_PARAMETERS

</td>
<td>
Service activation failed because of invalid parameters.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Service activation failed. Miniport drivers can return this value if service has already been
        activated.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
Service activation failed because the device requires a PIN.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_RADIO_POWER_OFF

</td>
<td>
Service activation failed because the radio is currently turned off.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
Service activation failed because a bad SIM card was detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
Service activation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PROVIDER_NOT_VISIBLE

</td>
<td>
Service activation failed because the service provider is not currently visible.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
Service activation failed because the device does not support service activation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to WwanReadyStateInitialized.

</td>
</tr>
</table>
 


### -field ServiceActivationStatus

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_service_activation_status">
     WWAN_SERVICE_ACTIVATION_STATUS</a> object that represents the status of service activation on the
     device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_service_activation_status">
   WWAN_SERVICE_ACTIVATION_STATUS</a>
 

 

