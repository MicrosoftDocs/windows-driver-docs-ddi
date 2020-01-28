---
UID: NE:ntddndis._NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE
title: _NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE (ntddndis.h)
description: The NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration specifies the type of status information for a proprietary policy property, or feature, of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_feature_status_type.htm
tech.root: netvista
ms.assetid: bdf19090-5688-4496-8f9a-3a1c422ede60
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortFeatureStatusTypeCustom, NdisSwitchPortFeatureStatusTypeMaximum, NdisSwitchPortFeatureStatusTypeUndefined, PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, netvista.ndis_switch_port_feature_status_type, ntddndis/NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, ntddndis/NdisSwitchPortFeatureStatusTypeCustom, ntddndis/NdisSwitchPortFeatureStatusTypeMaximum, ntddndis/NdisSwitchPortFeatureStatusTypeUndefined, ntddndis/PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE"
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE
---

# _NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration


## -description



The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE</b> enumeration specifies the type of status information for a proprietary policy property, or <i>feature</i>, of a Hyper-V extensible switch port.

An extensible switch port feature is defined and supported by an independent software vendor (ISV).




## -enum-fields




### -field NdisSwitchPortFeatureStatusTypeUndefined

The port feature status information is not defined.


### -field NdisSwitchPortFeatureStatusTypeCustom

The feature status information is for a custom extensible switch port feature that is provided by an ISV.




### -field NdisSwitchPortFeatureStatusTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>FeatureStatusType</b> member of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_feature_status_parameters">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure is an <b>NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE</b> enumeration data type.

For more information about extensible switch port policies, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-policies">Hyper-V Extensible Switch Policies</a>.






## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_feature_status_parameters">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>
 

 

