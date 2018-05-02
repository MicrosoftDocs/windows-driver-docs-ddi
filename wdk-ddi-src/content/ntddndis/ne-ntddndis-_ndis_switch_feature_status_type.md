---
UID: NE:ntddndis._NDIS_SWITCH_FEATURE_STATUS_TYPE
title: "_NDIS_SWITCH_FEATURE_STATUS_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration specifies the type of status information for a custom policy property, or feature, of a Hyper-V extensible switch.
old-location: netvista\ndis_switch_feature_status_type.htm
old-project: netvista
ms.assetid: a3255313-1d49-4286-a48a-6a1729ccf7fe
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_SWITCH_FEATURE_STATUS_TYPE, NDIS_SWITCH_FEATURE_STATUS_TYPE, NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchFeatureStatusTypeCustom, NdisSwitchFeatureStatusTypeMaximum, NdisSwitchFeatureStatusTypeUndefined, PNDIS_SWITCH_FEATURE_STATUS_TYPE, PNDIS_SWITCH_FEATURE_STATUS_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_FEATURE_STATUS_TYPE, netvista.ndis_switch_feature_status_type, ntddndis/NDIS_SWITCH_FEATURE_STATUS_TYPE, ntddndis/NdisSwitchFeatureStatusTypeCustom, ntddndis/NdisSwitchFeatureStatusTypeMaximum, ntddndis/NdisSwitchFeatureStatusTypeUndefined, ntddndis/PNDIS_SWITCH_FEATURE_STATUS_TYPE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_FEATURE_STATUS_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_FEATURE_STATUS_TYPE
---

# _NDIS_SWITCH_FEATURE_STATUS_TYPE enumeration


## -description



The <b>NDIS_SWITCH_FEATURE_STATUS_TYPE</b> enumeration specifies the type of status information for a custom policy property, or <i>feature</i>, of a Hyper-V extensible switch.

An extensible switch feature is defined and supported by an independent software vendor (ISV).




## -enum-fields




### -field NdisSwitchFeatureStatusTypeUndefined

The feature status information is not defined.


### -field NdisSwitchFeatureStatusTypeCustom

The feature status information is for a custom extensible switch feature that is provided by an ISV.




### -field NdisSwitchFeatureStatusTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>FeatureStatusType</b> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598208">NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</a> structure is an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598257">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration data type.

For more information about extensible switch  policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.






## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598208">NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</a>
 

 

