---
UID: NE:wdm._SYSTEM_POWER_STATE
title: _SYSTEM_POWER_STATE (wdm.h)
description: The SYSTEM_POWER_STATE enumeration type is used to indicate a system power state.
old-location: kernel\system_power_state.htm
tech.root: kernel
ms.assetid: aa027f03-7d74-4c0e-8f62-d53f41ae86ae
ms.date: 04/30/2018
ms.keywords: "*PSYSTEM_POWER_STATE, PSYSTEM_POWER_STATE, PSYSTEM_POWER_STATE enumeration pointer [Kernel-Mode Driver Architecture], PowerSystemHibernate, PowerSystemMaximum, PowerSystemShutdown, PowerSystemSleeping1, PowerSystemSleeping2, PowerSystemSleeping3, PowerSystemUnspecified, PowerSystemWorking, SYSTEM_POWER_STATE, SYSTEM_POWER_STATE enumeration [Kernel-Mode Driver Architecture], _SYSTEM_POWER_STATE, kernel.system_power_state, sysenum_32377b1c-a5d3-491b-aebd-ee3d40798f73.xml, wdm/PSYSTEM_POWER_STATE, wdm/PowerSystemHibernate, wdm/PowerSystemMaximum, wdm/PowerSystemShutdown, wdm/PowerSystemSleeping1, wdm/PowerSystemSleeping2, wdm/PowerSystemSleeping3, wdm/PowerSystemUnspecified, wdm/PowerSystemWorking, wdm/SYSTEM_POWER_STATE"
f1_keywords:
 - "wdm/SYSTEM_POWER_STATE"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h
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
- Wdm.h
api_name:
- SYSTEM_POWER_STATE
product:
- Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE, *PSYSTEM_POWER_STATE
---

# _SYSTEM_POWER_STATE enumeration


## -description


The <b>SYSTEM_POWER_STATE</b> enumeration type is used to indicate a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-states">system power state</a>.


## -enum-fields




### -field PowerSystemUnspecified

Indicates an unspecified system power state. 


### -field PowerSystemWorking

Indicates maximum system power, which corresponds to <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state S0</a>. 


### -field PowerSystemSleeping1

Indicates a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-sleeping-states">system sleeping state</a> less than <b>PowerSystemWorking</b> and greater than <b>PowerSystemSleeping2</b>, which corresponds to system power state S1. 


### -field PowerSystemSleeping2

Indicates a system sleeping state less than <b>PowerSystemSleeping1</b> and greater than <b>PowerSystemSleeping3</b>, which corresponds to system power state S2. 


### -field PowerSystemSleeping3

Indicates a system sleeping state less than <b>PowerSystemSleeping2</b> and greater than <b>PowerSystemHibernate</b>, which corresponds to system power state S3. 


### -field PowerSystemHibernate

Indicates the lowest-powered sleeping state, which corresponds to system power state S4. 


### -field PowerSystemShutdown

Indicates the system is turned off, which corresponds to <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-shutdown-state-s5">system shutdown state S5</a>. 


### -field PowerSystemMaximum

The number of system power state values for this enumeration type that represents actual power states. This value is the number of elements in the <b>DeviceState</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_capabilities">DEVICE_CAPABILITIES</a> structure for a device. The other system power state values are less than this value.


## -remarks



A power state indicates the level of power consumption—and thus the extent of computing activity—by the system or by a single device. The power manager sets the power state of the system as a whole, where the system power state is indicated by one of the values of the <b>SYSTEM_POWER_STATE</b> enumeration type. Device drivers set the power state of their individual devices, where the device power state is indicated by one of the values of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a> enumeration type.

For more information about system power states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-system-power-state-requests">Handling System Power State Requests</a> and for more information about device power states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-power-for-individual-devices">Managing Power for Individual Devices</a>.

For more information about power management in general, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-power-management">Introduction to Power Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>
 

 

