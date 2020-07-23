---
UID: NS:ndiswwan._NDIS_WWAN_SET_SMS_CONFIGURATION
title: _NDIS_WWAN_SET_SMS_CONFIGURATION (ndiswwan.h)
description: The NDIS_WWAN_SET_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.
old-location: netvista\ndis_wwan_set_sms_configuration.htm
tech.root: netvista
ms.assetid: aa191c47-4b3b-464a-8a12-db673fca0f20
ms.date: 05/02/2018
keywords: ["_NDIS_WWAN_SET_SMS_CONFIGURATION structure"]
ms.keywords: "*PNDIS_WWAN_SET_SMS_CONFIGURATION, NDIS_WWAN_SET_SMS_CONFIGURATION, NDIS_WWAN_SET_SMS_CONFIGURATION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_SMS_CONFIGURATION, PNDIS_WWAN_SET_SMS_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], WwanRef_f118e481-c8ed-4b8b-a6f9-ba1e26fc564f.xml, _NDIS_WWAN_SET_SMS_CONFIGURATION, ndiswwan/NDIS_WWAN_SET_SMS_CONFIGURATION, ndiswwan/PNDIS_WWAN_SET_SMS_CONFIGURATION, netvista.ndis_wwan_set_sms_configuration"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SET_SMS_CONFIGURATION"
 - "NDIS_WWAN_SET_SMS_CONFIGURATION"
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
- NDIS_WWAN_SET_SMS_CONFIGURATION
targetos: Windows
req.typenames: NDIS_WWAN_SET_SMS_CONFIGURATION, *PNDIS_WWAN_SET_SMS_CONFIGURATION
---

# _NDIS_WWAN_SET_SMS_CONFIGURATION structure


## -description


The NDIS_WWAN_SET_SMS_CONFIGURATION structure represents the SMS configuration of the MB
  device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_SMS_CONFIGURATION
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
NDIS_WWAN_SET_SMS_CONFIGURATION_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_SMS_CONFIGURATION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field SetSmsConfiguration

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_sms_configuration">
     WWAN_SET_SMS_CONFIGURATION</a> object that represents the SMS configuration to set on the
     device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_sms_configuration">WWAN_SET_SMS_CONFIGURATION</a>
 

 

