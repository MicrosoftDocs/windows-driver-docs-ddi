---
UID: NE:wdm._DEVICE_POWER_STATE
title: _DEVICE_POWER_STATE (wdm.h)
description: The DEVICE_POWER_STATE enumeration type indicates a device power state.
old-location: kernel\device_power_state.htm
tech.root: kernel
ms.assetid: d3166685-2aec-4874-a5a9-8cc293a96a2c
ms.date: 04/30/2018
keywords: ["_DEVICE_POWER_STATE enumeration"]
ms.keywords: "*PDEVICE_POWER_STATE, DEVICE_POWER_STATE, DEVICE_POWER_STATE enumeration [Kernel-Mode Driver Architecture], PDEVICE_POWER_STATE, PDEVICE_POWER_STATE enumeration pointer [Kernel-Mode Driver Architecture], PowerDeviceD0, PowerDeviceD1, PowerDeviceD2, PowerDeviceD3, PowerDeviceMaximum, PowerDeviceUnspecified, _DEVICE_POWER_STATE, kernel.device_power_state, sysenum_4f65cc59-f3a2-42ef-a8bb-7a2d178a6be7.xml, wdm/DEVICE_POWER_STATE, wdm/PDEVICE_POWER_STATE, wdm/PowerDeviceD0, wdm/PowerDeviceD1, wdm/PowerDeviceD2, wdm/PowerDeviceD3, wdm/PowerDeviceMaximum, wdm/PowerDeviceUnspecified"
f1_keywords:
 - "wdm/DEVICE_POWER_STATE"
 - "DEVICE_POWER_STATE"
req.header: wdm.h
req.include-header: Wdm.h, Ntpoapi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- DEVICE_POWER_STATE
targetos: Windows
req.typenames: DEVICE_POWER_STATE, *PDEVICE_POWER_STATE
---

# _DEVICE_POWER_STATE enumeration


## -description


The <b>DEVICE_POWER_STATE</b> enumeration type indicates a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a>. 


## -enum-fields




### -field PowerDeviceUnspecified

Indicates an unspecified device power state. 


### -field PowerDeviceD0

Indicates a maximum device power state, which corresponds to <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-working-state-d0">device working state D0</a>. 


### -field PowerDeviceD1

Indicates a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-sleeping-states">device sleeping state</a> less than <b>PowerDeviceD0</b> and greater than <b>PowerDeviceD2</b>, which corresponds to device power state D1.


### -field PowerDeviceD2

Indicates a device sleeping state less than <b>PowerDeviceD1</b> and greater than <b>PowerDeviceD3</b>, which corresponds to device power state D2. 


### -field PowerDeviceD3

Indicates the lowest-powered device sleeping state, which corresponds to device power state D3.


### -field PowerDeviceMaximum

The number of device power state values for this enumeration type that represent actual power states. The value of the other device power states is less than this value. 


## -remarks



A power state indicates the level of power consumption—and thus the extent of computing activity—by the system or by a single device. The power manager sets the power state of the system as a whole, where the system power state is indicated by one of the values of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a> enumeration type. Device drivers set the power state of their individual devices, where the device power state is indicated by one of the values of the <b>DEVICE_POWER_STATE</b> enumeration type.

For more information about system power states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-system-power-state-requests">Handling System Power State Requests</a>. For more information about device power states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-power-for-individual-devices">Managing Power for Individual Devices</a>. For more information about power management in general, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-power-management">Introduction to Power Management</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a>
 

 

