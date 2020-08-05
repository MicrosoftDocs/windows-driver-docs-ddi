---
UID: NE:ntddndis._NDIS_SWITCH_NIC_STATE
title: _NDIS_SWITCH_NIC_STATE (ntddndis.h)
description: The NDIS_SWITCH_NIC_STATE enumeration specifies the current state of the Hyper-V extensible switch network adapter.
old-location: netvista\ndis_switch_nic_state.htm
tech.root: netvista
ms.assetid: 06FFECB3-0883-41CA-9BD3-A6A1D95D5F8C
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_NIC_STATE enumeration"]
ms.keywords: NDIS_SWITCH_NIC_STATE, NDIS_SWITCH_NIC_STATE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchNicStateConnected, NdisSwitchNicStateCreated, NdisSwitchNicStateDeleted, NdisSwitchNicStateDisconnected, NdisSwitchNicStateUnknown, _NDIS_SWITCH_NIC_STATE, netvista.ndis_switch_nic_state, ntddndis/NDIS_SWITCH_NIC_STATE, ntddndis/NdisSwitchNicStateConnected, ntddndis/NdisSwitchNicStateCreated, ntddndis/NdisSwitchNicStateDeleted, ntddndis/NdisSwitchNicStateDisconnected, ntddndis/NdisSwitchNicStateUnknown
f1_keywords:
 - "ntddndis/NDIS_SWITCH_NIC_STATE"
 - "NDIS_SWITCH_NIC_STATE"
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
- NDIS_SWITCH_NIC_STATE
targetos: Windows
req.typenames: NDIS_SWITCH_NIC_STATE
---

# _NDIS_SWITCH_NIC_STATE enumeration


## -description


The <b>NDIS_SWITCH_NIC_STATE</b> enumeration specifies the current state of the Hyper-V extensible switch network adapter. 


## -enum-fields




### -field NdisSwitchNicStateUnknown

       This value specifies an undefined NIC state. This value is unused. 


### -field NdisSwitchNicStateCreated

This value specifies that the NIC is in the created state. 


### -field NdisSwitchNicStateConnected

This value specifies that the NIC is connected.


### -field NdisSwitchNicStateDisconnected

This value specifies that the NIC is disconnected.


### -field NdisSwitchNicStateDeleted

This value specifies that the NIC is deleted.


## -remarks



The <b>NicState</b>  member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structure is an <b>NDIS_SWITCH_NIC_STATE</b> enumeration data type. 


For more information about extensible switch port states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-hyper-v-extensible-switch-network-adapters">Overview of Hyper-V Extensible Switch Network Adapters</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a>
 

 

