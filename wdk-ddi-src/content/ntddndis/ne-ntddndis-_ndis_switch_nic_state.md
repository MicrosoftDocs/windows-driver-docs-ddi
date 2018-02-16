---
UID: NE:ntddndis._NDIS_SWITCH_NIC_STATE
title: "_NDIS_SWITCH_NIC_STATE"
author: windows-driver-content
description: The NDIS_SWITCH_NIC_STATE enumeration specifies the current state of the Hyper-V extensible switch network adapter.
old-location: netvista\ndis_switch_nic_state.htm
old-project: netvista
ms.assetid: 06FFECB3-0883-41CA-9BD3-A6A1D95D5F8C
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NdisSwitchNicStateCreated, NdisSwitchNicStateConnected, ntddndis/NdisSwitchNicStateConnected, ntddndis/NDIS_SWITCH_NIC_STATE, NdisSwitchNicStateCreated, NdisSwitchNicStateUnknown, ntddndis/NdisSwitchNicStateDeleted, ntddndis/NdisSwitchNicStateUnknown, NDIS_SWITCH_NIC_STATE enumeration [Network Drivers Starting with Windows Vista], NDIS_SWITCH_NIC_STATE, ntddndis/NdisSwitchNicStateDisconnected, netvista.ndis_switch_nic_state, _NDIS_SWITCH_NIC_STATE, NdisSwitchNicStateDisconnected, NdisSwitchNicStateDeleted
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
-	NDIS_SWITCH_NIC_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_NIC_STATE
---

# _NDIS_SWITCH_NIC_STATE enumeration


## -description


The <b>NDIS_SWITCH_NIC_STATE</b> enumeration specifies the current state of the Hyper-V extensible switch network adapter. 


## -syntax


````
typedef enum _NDIS_SWITCH_NIC_STATE { 
  NdisSwitchNicStateUnknown       = 0,
  NdisSwitchNicStateCreated       = 1,
  NdisSwitchNicStateConnected     = 2,
  NdisSwitchNicStateDisconnected  = 3,
  NdisSwitchNicStateDeleted       = 4
} NDIS_SWITCH_NIC_STATE;
````


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



The <b>NicState</b>  member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a> structure is an <b>NDIS_SWITCH_NIC_STATE</b> enumeration data type. 


For more information about extensible switch port states, see <a href="https://msdn.microsoft.com/61403FDE-90BF-4D0A-83E1-5AF8ADBD37A5">Overview of Hyper-V Extensible Switch Network Adapters</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_NIC_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

