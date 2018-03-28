---
UID: NE:ntddndis._NDIS_NIC_SWITCH_VPORT_STATE
title: "_NDIS_NIC_SWITCH_VPORT_STATE"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_STATE enumeration specifies the state of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch of a network adapter.
old-location: netvista\ndis_nic_switch_vport_state.htm
old-project: netvista
ms.assetid: 25999016-95a8-4d78-a4a3-111fc4e910ad
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_STATE, NDIS_NIC_SWITCH_VPORT_STATE, NDIS_NIC_SWITCH_VPORT_STATE enumeration [Network Drivers Starting with Windows Vista], NdisNicSwitchVPortStateActivated, NdisNicSwitchVPortStateDeactivated, NdisNicSwitchVPortStateMaximum, NdisNicSwitchVPortStateUndefined, PNDIS_NIC_SWITCH_VPORT_STATE, PNDIS_NIC_SWITCH_VPORT_STATE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_STATE, netvista.ndis_nic_switch_vport_state, ntddndis/NDIS_NIC_SWITCH_VPORT_STATE, ntddndis/NdisNicSwitchVPortStateActivated, ntddndis/NdisNicSwitchVPortStateDeactivated, ntddndis/NdisNicSwitchVPortStateMaximum, ntddndis/NdisNicSwitchVPortStateUndefined, ntddndis/PNDIS_NIC_SWITCH_VPORT_STATE"
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
-	NDIS_NIC_SWITCH_VPORT_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_STATE, *PNDIS_NIC_SWITCH_VPORT_STATE
---

# _NDIS_NIC_SWITCH_VPORT_STATE enumeration


## -description


The <b>NDIS_NIC_SWITCH_VPORT_STATE</b> enumeration specifies the state of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch of a network adapter.


## -enum-fields




### -field NdisNicSwitchVPortStateUndefined

The VPort state is not defined.


### -field NdisNicSwitchVPortStateActivated

The VPort is allocated and in an activated state.

<div class="alert"><b>Note</b>  The default VPort attached to the PCI Express (PCIe) Physical Function (PF) and nondefault VPorts attached to PCIe Virtual Functions (VFs) are created in an activated state. Once created, these VPorts cannot be deactivated.</div>
<div> </div>

### -field NdisNicSwitchVPortStateDeactivated

The VPort is allocated and in a deactivated state.

<div class="alert"><b>Note</b>  Nondefault VPorts attached to the PF are created in a deactivated state. These VPorts can be activated by using OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. However, once activated, these VPorts cannot be deactivated.</div>
<div> </div>

### -field NdisNicSwitchVPortStateMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.


## -remarks



The <b>VPortState</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451597">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451594">NDIS_NIC_SWITCH_VPORT_INFO</a> structures is an <b>NDIS_NIC_SWITCH_VPORT_STATE</b> enumeration data type. 




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451594">NDIS_NIC_SWITCH_VPORT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451597">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_VPORT_STATE enumeration%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

