---
UID: NE:ntddndis._NDIS_NIC_SWITCH_TYPE
title: _NDIS_NIC_SWITCH_TYPE (ntddndis.h)
description: The NDIS_NIC_SWITCH_TYPE enumeration specifies the type of the NIC switch on a network adapter.
old-location: netvista\ndis_nic_switch_type.htm
tech.root: netvista
ms.assetid: F990F166-D9DA-43F5-95D3-86B9B11FACF1
ms.date: 05/02/2018
keywords: ["_NDIS_NIC_SWITCH_TYPE enumeration"]
ms.keywords: "*PNDIS_NIC_SWITCH_TYPE, NDIS_NIC_SWITCH_TYPE, NDIS_NIC_SWITCH_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisNicSwitchTypeExternal, NdisNicSwitchTypeMax, NdisNicSwitchTypeUnspecified, PNDIS_NIC_SWITCH_TYPE, PNDIS_NIC_SWITCH_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_TYPE, netvista.ndis_nic_switch_type, ntddndis/NDIS_NIC_SWITCH_TYPE, ntddndis/NdisNicSwitchTypeExternal, ntddndis/NdisNicSwitchTypeMax, ntddndis/NdisNicSwitchTypeUnspecified, ntddndis/PNDIS_NIC_SWITCH_TYPE"
f1_keywords:
 - "ntddndis/NDIS_NIC_SWITCH_TYPE"
 - "NDIS_NIC_SWITCH_TYPE"
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
- NDIS_NIC_SWITCH_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_TYPE, *PNDIS_NIC_SWITCH_TYPE
---

# _NDIS_NIC_SWITCH_TYPE enumeration


## -description


The <b>NDIS_NIC_SWITCH_TYPE</b> enumeration specifies the type of the NIC switch on a network adapter.




## -enum-fields




### -field NdisNicSwitchTypeUnspecified

The NIC switch type is not specified.


### -field NdisNicSwitchTypeExternal

This value specifies an external switch. The single root I/O virtualization (SR-IOV) virtual ports (VPorts) connected to this type of switch, including the default VPort, can access the external network through the physical port on the network adapter.


### -field NdisNicSwitchTypeMax

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>SwitchType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_parameters">NDIS_NIC_SWITCH_PARAMETERS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info">NDIS_NIC_SWITCH_INFO</a> structures is an <b>NDIS_NIC_SWITCH_TYPE</b> enumeration data type. 



For more information about the NIC switch, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/sr-iov-architecture">SR-IOV Architecture</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info">NDIS_NIC_SWITCH_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_parameters">NDIS_NIC_SWITCH_PARAMETERS</a>
 

 

