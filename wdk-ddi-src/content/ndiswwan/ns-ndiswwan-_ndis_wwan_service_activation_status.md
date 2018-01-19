---
UID: NS:ndiswwan._NDIS_WWAN_SERVICE_ACTIVATION_STATUS
title: _NDIS_WWAN_SERVICE_ACTIVATION_STATUS
author: windows-driver-content
description: The NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the MB device.
old-location: netvista\ndis_wwan_service_activation_status.htm
old-project: netvista
ms.assetid: 669ef35f-0e59-4ec3-b6cc-5cb2156b51a2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_SERVICE_ACTIVATION_STATUS, NDIS_WWAN_SERVICE_ACTIVATION_STATUS, *PNDIS_WWAN_SERVICE_ACTIVATION_STATUS
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
req.alt-api: NDIS_WWAN_SERVICE_ACTIVATION_STATUS
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
req.typenames: NDIS_WWAN_SERVICE_ACTIVATION_STATUS, *PNDIS_WWAN_SERVICE_ACTIVATION_STATUS
---

# _NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure



## -description
The NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the
  MB device.



## -syntax

````
typedef struct _NDIS_WWAN_SERVICE_ACTIVATION_STATUS {
  NDIS_OBJECT_HEADER             Header;
  WWAN_STATUS                    uStatus;
  WWAN_SERVICE_ACTIVATION_STATUS ServiceActivationStatus;
} NDIS_WWAN_SERVICE_ACTIVATION_STATUS, *PNDIS_WWAN_SERVICE_ACTIVATION_STATUS;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


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
     <a href="..\wwan\ns-wwan-_wwan_service_activation_status.md">
     WWAN_SERVICE_ACTIVATION_STATUS</a> object that represents the status of service activation on the
     device.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_service_activation_status.md">
   WWAN_SERVICE_ACTIVATION_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

