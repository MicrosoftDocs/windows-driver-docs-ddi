---
UID: NS:ndiswwan._NDIS_WWAN_REGISTRATION_STATE
title: "_NDIS_WWAN_REGISTRATION_STATE"
author: windows-driver-content
description: The NDIS_WWAN_REGISTRATION_STATE structure represents the registration state of the MB device.
old-location: netvista\ndis_wwan_registration_state.htm
tech.root: netvista
ms.assetid: 3e38880f-b242-400a-babf-531c8daf7a19
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_REGISTRATION_STATE, NDIS_WWAN_REGISTRATION_STATE, NDIS_WWAN_REGISTRATION_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_REGISTRATION_STATE, PNDIS_WWAN_REGISTRATION_STATE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_7f854298-d100-4b4c-8748-a7eb07c9ac38.xml, _NDIS_WWAN_REGISTRATION_STATE, ndiswwan/NDIS_WWAN_REGISTRATION_STATE, ndiswwan/PNDIS_WWAN_REGISTRATION_STATE, netvista.ndis_wwan_registration_state"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_REGISTRATION_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_REGISTRATION_STATE, *PNDIS_WWAN_REGISTRATION_STATE
---

# _NDIS_WWAN_REGISTRATION_STATE structure


## -description


The NDIS_WWAN_REGISTRATION_STATE structure represents the registration state of the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_REGISTRATION_STATE
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
Windows 8 miniport drivers should set this to NDIS_WWAN_REGISTRATION_STATE_REVISION_2. Windows 7 miniport drivers should set this to NDIS_WWAN_REGISTRATION_STATE_REVISION_1.

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_REGISTRATION_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

A miniport driver must set this to WWAN_STATUS_SUCCESS for unsolicited events
     (NDIS_STATUS_INDICATION::RequestId = 0). WWAN_STATUS_SUCCESS is also set for successful execution of the
     NDIS_WWAN_SET_REGISTER_STATE.
     

The following table shows the other possible error status codes.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
Device requires PIN value input.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Unable to get registration state.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The operation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
</table>
 

Miniport drivers can return the following error codes (in addition to the above listed) only in the
     event a PDP activation 
     <i>set</i> operation fails.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Unable to set registration state. More information is specified in 
        <b>uNwError</b> . For other error codes, 
        <b>uNwError</b> should be set to 0.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
CDMA-based devices must return this error code, if a 
        <i>set</i> registration request is for manual registration.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SERVICE_NOT_ACTIVATED

</td>
<td>
Service activation failed. Subscription expired. Device does not allow setting registration
        state.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PROVIDER_NOT_VISIBLE

</td>
<td>
Provider is not visible for registration. This is for manual registration.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_PARAMETERS

</td>
<td>
If the request is manual registration to a forbidden provider.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
The device is busy and unable to change the registration mode. This scenario can occur if the
        device does not permit changing the registration mode when a PDP context is activated.

</td>
</tr>
</table>
 


### -field RegistrationState

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571231">WWAN_REGISTRATION_STATE</a> object that
     represents the registration state of the MB device.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571231">WWAN_REGISTRATION_STATE</a>
 

 

