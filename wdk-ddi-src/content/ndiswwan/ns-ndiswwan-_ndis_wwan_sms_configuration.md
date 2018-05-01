---
UID: NS:ndiswwan._NDIS_WWAN_SMS_CONFIGURATION
title: "_NDIS_WWAN_SMS_CONFIGURATION"
author: windows-driver-content
description: The NDIS_WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.
old-location: netvista\ndis_wwan_sms_configuration.htm
old-project: netvista
ms.assetid: 77d62078-7421-40c7-b743-fbc09b0eb5f9
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_WWAN_SMS_CONFIGURATION, NDIS_WWAN_SMS_CONFIGURATION, NDIS_WWAN_SMS_CONFIGURATION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_CONFIGURATION, PNDIS_WWAN_SMS_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], WwanRef_29c93c56-0878-421c-a690-aa5d3ba2e64a.xml, _NDIS_WWAN_SMS_CONFIGURATION, ndiswwan/NDIS_WWAN_SMS_CONFIGURATION, ndiswwan/PNDIS_WWAN_SMS_CONFIGURATION, netvista.ndis_wwan_sms_configuration"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SMS_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SMS_CONFIGURATION, *PNDIS_WWAN_SMS_CONFIGURATION
---

# _NDIS_WWAN_SMS_CONFIGURATION structure


## -description


The NDIS_WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SMS_CONFIGURATION
     structure. When the MB Service
     sends the data structure to the miniport driver for 
     <i>set</i> operations, it sets the header with the values that are shown in the following table. Miniport drivers must set the header with the same values when they send the data
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
NDIS_WWAN_SMS_CONFIGURATION_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_CONFIGURATION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the SMS configuration operation. The following table shows the possible values for
     this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
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
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The operation failed because the device requires a PIN.

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
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a faulty SIM card was detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SMS_UNKNOWN_ERROR

</td>
<td>
The operation failed because of an unknown error.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SMS_FORMAT_NOT_SUPPORTED

</td>
<td>
The operation failed because the SMS format specified in <a href="https://msdn.microsoft.com/library/windows/hardware/ff571244">WWAN_SMS_CONFIGURATION</a> is not supported.

</td>
</tr>
</table>
 


### -field SmsConfiguration

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571244">WWAN_SMS_CONFIGURATION</a> object that
     represents the SMS configuration of the MB device.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571244">WWAN_SMS_CONFIGURATION</a>
 

 

