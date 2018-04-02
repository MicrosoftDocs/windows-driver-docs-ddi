---
UID: NE:ntddndis._NDIS_DEVICE_POWER_STATE
title: "_NDIS_DEVICE_POWER_STATE"
author: windows-driver-content
description: The NDIS_DEVICE_POWER_STATE enumeration defines device power state values.
old-location: netvista\ndis_device_power_state.htm
old-project: netvista
ms.assetid: d241b0ee-7b13-453d-ac6a-015b82effb95
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_DEVICE_POWER_STATE, NDIS_DEVICE_POWER_STATE, NDIS_DEVICE_POWER_STATE enumeration [Network Drivers Starting with Windows Vista], NdisDeviceStateD0, NdisDeviceStateD1, NdisDeviceStateD2, NdisDeviceStateD3, NdisDeviceStateMaximum, NdisDeviceStateUnspecified, PNDIS_DEVICE_POWER_STATE, PNDIS_DEVICE_POWER_STATE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_DEVICE_POWER_STATE, netvista.ndis_device_power_state, ntddndis/NDIS_DEVICE_POWER_STATE, ntddndis/NdisDeviceStateD0, ntddndis/NdisDeviceStateD1, ntddndis/NdisDeviceStateD2, ntddndis/NdisDeviceStateD3, ntddndis/NdisDeviceStateMaximum, ntddndis/NdisDeviceStateUnspecified, ntddndis/PNDIS_DEVICE_POWER_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ntddndis.h
api_name:
-	NDIS_DEVICE_POWER_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_DEVICE_POWER_STATE, *PNDIS_DEVICE_POWER_STATE
---

# _NDIS_DEVICE_POWER_STATE enumeration


## -description


The <b>NDIS_DEVICE_POWER_STATE</b> enumeration defines device power state values. For more information about device power states, see:<dl>
<dd>
<a href="https://msdn.microsoft.com/969aadc9-e797-4a07-9714-8c2c5a6357da">Device Power States for Network Adapters</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543210">Device Working State D0</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543186">Device Low-Power States</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561073">Required Support for Device Power States</a>
</dd>
</dl>



## -enum-fields




### -field NdisDeviceStateUnspecified

The device does not support power management.


### -field NdisDeviceStateD0

Device power state D0.


### -field NdisDeviceStateD1

Device power state D1.


### -field NdisDeviceStateD2

Device power state D2.


### -field NdisDeviceStateD3

Device power state D3.


### -field NdisDeviceStateMaximum

The maximum value for this enumeration. Reserved for system use. Do not use this value in your driver. This value might change in future versions of NDIS header files and binaries.




## -remarks



Depending on the capabilities of the network adapter and its miniport driver, the device might be able to generate a wake-up signal from device states D0 through D3.

<div class="alert"><b>Note</b>  If the wake-up signal is generated from D0, the signal does not cause a system wake-up. However, the wake-up signal can be used to signal a run-time event.</div>
<div> </div>
<b>NDIS_DEVICE_POWER_STATE</b> enumeration values are used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566748">NDIS_PM_CAPABILITIES</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh451683">NDIS_SRIOV_SET_VF_POWER_STATE_PARAMETERS</a>,  and <a href="https://msdn.microsoft.com/library/windows/hardware/ff568751">NET_PNP_EVENT</a> structures, the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451492">NdisMIdleNotificationConfirm</a> function, and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff569778">OID_PNP_QUERY_POWER</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff569780">OID_PNP_SET_POWER</a> OID requests.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566748">NDIS_PM_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451683">NDIS_SRIOV_SET_VF_POWER_STATE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568751">NET_PNP_EVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451492">NdisMIdleNotificationConfirm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569778">OID_PNP_QUERY_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569780">OID_PNP_SET_POWER</a>
 

 

