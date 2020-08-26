---
UID: NS:pepfx._PEP_DEVICE_POWER_STATE
title: _PEP_DEVICE_POWER_STATE (pepfx.h)
description: The PEP_DEVICE_POWER_STATE structure indicates the status of a transition to a new Dx (device power) state.
old-location: kernel\pep_device_power_state.htm
tech.root: kernel
ms.assetid: F5E66C33-F727-4631-89C6-413C24995A04
ms.date: 04/30/2018
keywords: ["PEP_DEVICE_POWER_STATE structure"]
ms.keywords: "*PPEP_DEVICE_POWER_STATE, PEP_DEVICE_POWER_STATE, PEP_DEVICE_POWER_STATE structure [Kernel-Mode Driver Architecture], PPEP_DEVICE_POWER_STATE, PPEP_DEVICE_POWER_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_DEVICE_POWER_STATE, kernel.pep_device_power_state, pepfx/PEP_DEVICE_POWER_STATE, pepfx/PPEP_DEVICE_POWER_STATE"
f1_keywords:
 - "pepfx/PEP_DEVICE_POWER_STATE"
 - "PEP_DEVICE_POWER_STATE"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
- pepfx.h
api_name:
- PEP_DEVICE_POWER_STATE
targetos: Windows
req.typenames: PEP_DEVICE_POWER_STATE, *PPEP_DEVICE_POWER_STATE
---

# _PEP_DEVICE_POWER_STATE structure


## -description


The <b>PEP_DEVICE_POWER_STATE</b> structure indicates the status of a transition to a new D<i>x</i> (device power) state.


## -struct-fields




### -field DeviceHandle

[in] The PEPHANDLE value that identifies this device. The PEP previously created this handle in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification from the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx).


### -field PowerState

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a> enumeration value that specifies the new device power state.


### -field Complete

[in] Whether the transition to the new device power state has just been initiated or has just completed. If TRUE, the transition to the target device power state has completed. If FALSE, the power policy owner (PPO) has initiated the transition by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a> routine, but the Windows power manager has not yet issued the D<i>x</i> IRP (an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a> request of type <b>DevicePowerState</b>) to the device's driver stack.


### -field SystemTransition

[in] Always set to FALSE.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_DEVICE_POWER_STATE</a> notification. All four members of the structure contain input values that are supplied by PoFx. The PEP does not write to this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_DEVICE_POWER_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a>
 

 

