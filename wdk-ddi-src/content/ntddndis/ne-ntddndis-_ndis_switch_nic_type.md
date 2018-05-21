---
UID: NE:ntddndis._NDIS_SWITCH_NIC_TYPE
title: "_NDIS_SWITCH_NIC_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_NIC_TYPE enumeration specifies the type of the virtual network adapter that is attached to a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_nic_type.htm
old-project: netvista
ms.assetid: 0ff7a803-9de4-4b2f-ab5f-3eb5107d5b64
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDIS_SWITCH_NIC_TYPE, NDIS_SWITCH_NIC_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchNicTypeEmulated, NdisSwitchNicTypeExternal, NdisSwitchNicTypeInternal, NdisSwitchNicTypeSynthetic, PNDIS_SWITCH_NIC_TYPE, PNDIS_SWITCH_NIC_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_NIC_TYPE, netvista.ndis_switch_nic_type, ntddndis/NDIS_SWITCH_NIC_TYPE, ntddndis/NdisSwitchNicTypeEmulated, ntddndis/NdisSwitchNicTypeExternal, ntddndis/NdisSwitchNicTypeInternal, ntddndis/NdisSwitchNicTypeSynthetic, ntddndis/PNDIS_SWITCH_NIC_TYPE
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
-	NDIS_SWITCH_NIC_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_NIC_TYPE
---

# _NDIS_SWITCH_NIC_TYPE enumeration


## -description


The <b>NDIS_SWITCH_NIC_TYPE</b> enumeration specifies the type of the virtual network adapter that is attached to a Hyper-V extensible switch port.




## -enum-fields




### -field NdisSwitchNicTypeExternal

This value specifies a virtual network adapter that is exposed in the management operating system that runs in the Hyper-V parent partition. The external network adapter provides the connection to the  physical network interface that is available on the host. This allows processes that run in either the management or guest operating systems to send or receive packets over the extensible switch.

<div class="alert"><b>Note</b>  An extensible switch supports no more than one external network adapter. The external network adapter can be bound to one or more underlying physical network adapters. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/external-network-adapters">External Network Adapters</a>.</div>
<div> </div>

### -field NdisSwitchNicTypeSynthetic

This value specifies a synthetic network adapter that is exposed in a guest operating system that runs in a Hyper-V child partition.

<div class="alert"><b>Note</b>  A synthetic network adapter is a type of virtual machine (VM) network adapter. This adapter is exposed in a guest operating system that is Windows Vista or a later version of Windows.</div>
<div> </div>

### -field NdisSwitchNicTypeEmulated

This value specifies an emulated network adapter that is exposed in a guest operating system.

<div class="alert"><b>Note</b>  An emulated network adapter is a type of VM network adapter. This adapter is exposed in a guest operating system that is Windows XP, Windows Vista, or a later version of Windows. This adapter is also exposed in a guest operating system that is a non-Windows operating system.</div>
<div> </div>

### -field NdisSwitchNicTypeInternal

This value specifies a virtual network adapter that is exposed in the management operating system that runs in the Hyper-V parent partition. The internal network adapter provides access to an extensible switch for processes that run in the management operating system. This allows these processes to send or receive packets over the extensible switch.

<div class="alert"><b>Note</b>  An extensible switch supports no more than one internal network adapter. For more information, see <a href="https://msdn.microsoft.com/4E4B0EC9-8E4C-47FC-B608-EC6D18367A79">Internal Network Adapters</a>.</div>
<div> </div>

## -remarks



The <b>NicType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598215">NDIS_SWITCH_NIC_PARAMETERS</a> structure is an <b>NDIS_SWITCH_NIC_TYPE</b> enumeration data type. 



For more information on the types of network adapters that connect to extensible switch ports, see <a href="https://msdn.microsoft.com/30FBB908-74C1-480B-8DA7-B1334964BF53">Hyper-V Extensible Switch Network Adapters</a>.






## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598215">NDIS_SWITCH_NIC_PARAMETERS</a>
 

 

