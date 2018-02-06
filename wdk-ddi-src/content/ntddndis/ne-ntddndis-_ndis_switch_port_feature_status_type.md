---
UID: NE:ntddndis._NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE
title: "_NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration specifies the type of status information for a proprietary policy property, or feature, of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_feature_status_type.htm
old-project: netvista
ms.assetid: bdf19090-5688-4496-8f9a-3a1c422ede60
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NdisSwitchPortFeatureStatusTypeMaximum, PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], NdisSwitchPortFeatureStatusTypeCustom, ntddndis/NdisSwitchPortFeatureStatusTypeCustom, NdisSwitchPortFeatureStatusTypeUndefined, ntddndis/NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, NdisSwitchPortFeatureStatusTypeMaximum, _NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, ntddndis/NdisSwitchPortFeatureStatusTypeUndefined, PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, netvista.ndis_switch_port_feature_status_type
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE
---

# _NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration


## -description



The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE</b> enumeration specifies the type of status information for a proprietary policy property, or <i>feature</i>, of a Hyper-V extensible switch port.

An extensible switch port feature is defined and supported by an independent software vendor (ISV).




## -syntax


````
typedef enum _NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE { 
  NdisSwitchPortFeatureStatusTypeUndefined,
  NdisSwitchPortFeatureStatusTypeCustom,
  NdisSwitchPortFeatureStatusTypeMaximum
} NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE, *PNDIS_SWITCH_PORT_FEATURE_STATUS_TYPE;
````


## -enum-fields




### -field NdisSwitchPortFeatureStatusTypeUndefined

The port feature status information is not defined.


### -field NdisSwitchPortFeatureStatusTypeCustom

The feature status information is for a custom extensible switch port feature that is provided by an ISV.




### -field NdisSwitchPortFeatureStatusTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks


The <b>FeatureStatusType</b> member of the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure is an <b>NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE</b> enumeration data type.

For more information about extensible switch port policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.





## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

