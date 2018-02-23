---
UID: NE:ntddndis._NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
title: "_NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch.
old-location: netvista\ndis_nic_switch_vport_interrupt_moderation.htm
old-project: netvista
ms.assetid: 86ec2e8f-1a89-4c0a-b761-d9bf0d3dc35a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration pointer [Network Drivers Starting with Windows Vista], NdisNicSwitchVPortIntModMedium, ntddndis/NdisNicSwitchVPortIntModMedium, *PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, ntddndis/NdisNicSwitchVPortIntModHigh, NdisNicSwitchVPortIntModAdaptive, NdisNicSwitchVPortIntModOff, PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, ntddndis/NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, NdisNicSwitchVPortIntModUndefined, _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, ntddndis/NdisNicSwitchVPortIntModAdaptive, netvista.ndis_nic_switch_vport_interrupt_moderation, ntddndis/NdisNicSwitchVPortIntModUndefined, ntddndis/NdisNicSwitchVPortIntModOff, NdisNicSwitchVPortIntModLow, NdisNicSwitchVPortIntModHigh, ntddndis/NdisNicSwitchVPortIntModLow, NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, ntddndis/PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
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
-	NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, *PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
---

# _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration


## -description


The <b>NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION</b> enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch.


## -syntax


````
typedef enum _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION { 
  NdisNicSwitchVPortIntModUndefined  = 0,
  NdisNicSwitchVPortIntModAdaptive   = 1,
  NdisNicSwitchVPortIntModOff        = 2,
  NdisNicSwitchVPortIntModLow        = 100,
  NdisNicSwitchVPortIntModMedium     = 200,
  NdisNicSwitchVPortIntModHigh       = 300
} NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, *PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION;
````


## -enum-fields




### -field NdisNicSwitchVPortInterruptModerationUndefined


### -field NdisNicSwitchVPortInterruptModerationAdaptive


### -field NdisNicSwitchVPortInterruptModerationOff


### -field NdisNicSwitchVPortInterruptModerationLow


### -field NdisNicSwitchVPortInterruptModerationMedium


### -field NdisNicSwitchVPortInterruptModerationHigh




#### - NdisNicSwitchVPortIntModUndefined

Interrupt moderation for the VPort is not defined.


#### - NdisNicSwitchVPortIntModAdaptive

Interrupt moderation for the VPort is adaptive. This state enables the network adapter to adjust the interrupt moderation rate for the VPort based on the pattern of network traffic.


#### - NdisNicSwitchVPortIntModOff

Interrupt moderation for the VPort is disabled.


#### - NdisNicSwitchVPortIntModLow

Interrupt moderation for the VPort is low.


#### - NdisNicSwitchVPortIntModMedium

Interrupt moderation for the VPort is medium.


#### - NdisNicSwitchVPortIntModHigh

Interrupt moderation for the VPort is high.


## -remarks



The determination of low, medium, and high interrupt moderation levels is determined by the miniport driver based on a hardware algorithm that is based on the network adapter.

The <b>InterruptModeration</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_parameters.md">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a> and <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_info.md">NDIS_NIC_SWITCH_VPORT_INFO</a> structures is an NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration data type. 




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_parameters.md">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_info.md">NDIS_NIC_SWITCH_VPORT_INFO</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

