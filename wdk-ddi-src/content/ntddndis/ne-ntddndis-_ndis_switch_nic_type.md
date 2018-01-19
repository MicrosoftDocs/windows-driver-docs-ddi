---
UID: NE:ntddndis._NDIS_SWITCH_NIC_TYPE
title: _NDIS_SWITCH_NIC_TYPE
author: windows-driver-content
description: The NDIS_SWITCH_NIC_TYPE enumeration specifies the type of the virtual network adapter that is attached to a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_nic_type.htm
old-project: netvista
ms.assetid: 0ff7a803-9de4-4b2f-ab5f-3eb5107d5b64
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_SWITCH_NIC_TYPE, NDIS_SWITCH_NIC_TYPE
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
req.alt-api: NDIS_SWITCH_NIC_TYPE
req.alt-loc: Ntddndis.h
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
req.typenames: NDIS_SWITCH_NIC_TYPE
---

# _NDIS_SWITCH_NIC_TYPE enumeration



## -description
The <b>NDIS_SWITCH_NIC_TYPE</b> enumeration specifies the type of the virtual network adapter that is attached to a Hyper-V extensible switch port.





## -syntax

````
typedef enum _NDIS_SWITCH_NIC_TYPE { 
  NdisSwitchNicTypeExternal   = 0,
  NdisSwitchNicTypeSynthetic  = 1,
  NdisSwitchNicTypeEmulated   = 2,
  NdisSwitchNicTypeInternal   = 3
} NDIS_SWITCH_NIC_TYPE, *PNDIS_SWITCH_NIC_TYPE;
````


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
The <b>NicType</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a> structure is an <b>NDIS_SWITCH_NIC_TYPE</b> enumeration data type. 



For more information on the types of network adapters that connect to extensible switch ports, see <a href="https://msdn.microsoft.com/30FBB908-74C1-480B-8DA7-B1334964BF53">Hyper-V Extensible Switch Network Adapters</a>.




## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_NIC_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

