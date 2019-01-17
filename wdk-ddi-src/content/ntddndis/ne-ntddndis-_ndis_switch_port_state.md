---
UID: NE:ntddndis._NDIS_SWITCH_PORT_STATE
title: "_NDIS_SWITCH_PORT_STATE"
description: The NDIS_SWITCH_PORT_STATE enumeration specifies the current state of the Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_state.htm
tech.root: netvista
ms.assetid: BEF37F32-036D-4381-93B3-C159ABCFC3F9
ms.date: 05/02/2018
ms.keywords: NDIS_SWITCH_PORT_STATE, NDIS_SWITCH_PORT_STATE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortStateCreated, NdisSwitchPortStateDeleted, NdisSwitchPortStateTeardown, NdisSwitchPortStateUnknown, _NDIS_SWITCH_PORT_STATE, netvista.ndis_switch_port_state, ntddndis/NDIS_SWITCH_PORT_STATE, ntddndis/NdisSwitchPortStateCreated, ntddndis/NdisSwitchPortStateDeleted, ntddndis/NdisSwitchPortStateTeardown, ntddndis/NdisSwitchPortStateUnknown
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
-	NDIS_SWITCH_PORT_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_STATE
---

# _NDIS_SWITCH_PORT_STATE enumeration


## -description


The <b>NDIS_SWITCH_PORT_STATE</b> enumeration specifies the current state of the Hyper-V extensible switch port. 


## -enum-fields




### -field NdisSwitchPortStateUnknown

This value specifies an undefined port state. This value is unused.


### -field NdisSwitchPortStateCreated

This value specifies that the port is in the created state. 


### -field NdisSwitchPortStateTeardown

This value specifies that the port is being torn down.


### -field NdisSwitchPortStateDeleted

This value specifies that the port has been deleted. 


## -remarks



The <b>PortState</b>  member of the <a href="https://msdn.microsoft.com/E68A9018-1E79-4DA6-8C7A-434A2468169F">NDIS_SWITCH_PORT_PARAMETER</a> structure is an <b>NDIS_SWITCH_PORT_STATE</b> enumeration data type. 


For more information about extensible switch port states, see <a href="https://msdn.microsoft.com/FD6B6014-B840-4EC8-96F4-34C08EC303EA">Overview of Hyper-V Extensible Switch Ports</a>. 





## -see-also




<b></b>



<a href="https://msdn.microsoft.com/E68A9018-1E79-4DA6-8C7A-434A2468169F">NDIS_SWITCH_PORT_PARAMETER</a>
 

 

