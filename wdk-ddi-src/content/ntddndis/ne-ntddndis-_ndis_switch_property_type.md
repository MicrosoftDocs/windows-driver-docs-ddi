---
UID: NE:ntddndis._NDIS_SWITCH_PROPERTY_TYPE
title: "_NDIS_SWITCH_PROPERTY_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_TYPE enumeration specifies the type of policy property for a Hyper-V extensible switch.
old-location: netvista\ndis_switch_property_type.htm
old-project: netvista
ms.assetid: baa1b837-6f9b-41f4-acf8-e640f8e9f8da
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_SWITCH_PROPERTY_TYPE, NDIS_SWITCH_PROPERTY_TYPE, NDIS_SWITCH_PROPERTY_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPropertyTypeCustom, NdisSwitchPropertyTypeMaximum, NdisSwitchPropertyTypeUndefined, PNDIS_SWITCH_PROPERTY_TYPE, PNDIS_SWITCH_PROPERTY_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PROPERTY_TYPE, netvista.ndis_switch_property_type, ntddndis/NDIS_SWITCH_PROPERTY_TYPE, ntddndis/NdisSwitchPropertyTypeCustom, ntddndis/NdisSwitchPropertyTypeMaximum, ntddndis/NdisSwitchPropertyTypeUndefined, ntddndis/PNDIS_SWITCH_PROPERTY_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PROPERTY_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PROPERTY_TYPE, *PNDIS_SWITCH_PROPERTY_TYPE
---

# _NDIS_SWITCH_PROPERTY_TYPE enumeration


## -description


The <b>NDIS_SWITCH_PROPERTY_TYPE</b> enumeration specifies the type of policy property for a Hyper-V extensible switch.


## -enum-fields




### -field NdisSwitchPropertyTypeUndefined

The switch property type is not defined.


### -field NdisSwitchPropertyTypeCustom

This value specifies a custom switch property that is defined  by an independent software vendor (ISV).


### -field NdisSwitchPropertyTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>PropertyType</b> member of the following structures is an <b>NDIS_SWITCH_PROPERTY_TYPE</b> enumeration data type: 



<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598249">NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598253">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598255">NDIS_SWITCH_PROPERTY_PARAMETERS</a>


</li>
</ul>
For more information about extensible switch  policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.






## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598249">NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598253">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598255">NDIS_SWITCH_PROPERTY_PARAMETERS</a>
 

 

