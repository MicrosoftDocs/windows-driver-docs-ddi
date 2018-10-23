---
UID: NS:ndiswwan._NDIS_WWAN_DRIVER_CAPS
title: "_NDIS_WWAN_DRIVER_CAPS"
author: windows-driver-content
description: The NDIS_WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.
old-location: netvista\ndis_wwan_driver_caps.htm
tech.root: netvista
ms.assetid: 413ea129-2c55-4e7f-ad7c-ce99840f7066
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_DRIVER_CAPS, NDIS_WWAN_DRIVER_CAPS, NDIS_WWAN_DRIVER_CAPS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DRIVER_CAPS, PNDIS_WWAN_DRIVER_CAPS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_9c8d6cfb-7f4b-47ac-879b-4c3ada7f9239.xml, _NDIS_WWAN_DRIVER_CAPS, ndiswwan/NDIS_WWAN_DRIVER_CAPS, ndiswwan/PNDIS_WWAN_DRIVER_CAPS, netvista.ndis_wwan_driver_caps"
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
-	NDIS_WWAN_DRIVER_CAPS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DRIVER_CAPS, *PNDIS_WWAN_DRIVER_CAPS
---

# _NDIS_WWAN_DRIVER_CAPS structure


## -description


The NDIS_WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DRIVER_CAPS structure.
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
  NDIS_WWAN_DRIVER_CAPS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DRIVER_CAPS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field DriverCaps

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571206">WWAN_DRIVER_CAPS</a> structure that represents
     the capabilities of the miniport driver.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571206">WWAN_DRIVER_CAPS</a>
 

 

