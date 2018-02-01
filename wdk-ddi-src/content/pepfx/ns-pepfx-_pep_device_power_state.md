---
UID: NS:pepfx._PEP_DEVICE_POWER_STATE
title: "_PEP_DEVICE_POWER_STATE"
author: windows-driver-content
description: The PEP_DEVICE_POWER_STATE structure indicates the status of a transition to a new Dx (device power) state.
old-location: kernel\pep_device_power_state.htm
old-project: kernel
ms.assetid: F5E66C33-F727-4631-89C6-413C24995A04
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PPEP_DEVICE_POWER_STATE, PPEP_DEVICE_POWER_STATE, _PEP_DEVICE_POWER_STATE, PPEP_DEVICE_POWER_STATE structure pointer [Kernel-Mode Driver Architecture], PEP_DEVICE_POWER_STATE, kernel.pep_device_power_state, PEP_DEVICE_POWER_STATE structure [Kernel-Mode Driver Architecture], pepfx/PPEP_DEVICE_POWER_STATE, pepfx/PEP_DEVICE_POWER_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_DEVICE_POWER_STATE
product: Windows
targetos: Windows
req.typenames: PEP_DEVICE_POWER_STATE, *PPEP_DEVICE_POWER_STATE
---

# _PEP_DEVICE_POWER_STATE structure


## -description


The <b>PEP_DEVICE_POWER_STATE</b> structure indicates the status of a transition to a new D<i>x</i> (device power) state.


## -syntax


````
typedef struct _PEP_DEVICE_POWER_STATE {
  PEPHANDLE          DeviceHandle;
  DEVICE_POWER_STATE PowerState;
  BOOLEAN            Complete;
  BOOLEAN            SystemTransition;
} PEP_DEVICE_POWER_STATE, *PPEP_DEVICE_POWER_STATE;
````


## -struct-fields




### -field DeviceHandle

[in] The PEPHANDLE value that identifies this device. The PEP previously created this handle in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification from the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).


### -field PowerState

[in] A <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> enumeration value that specifies the new device power state.


### -field Complete

[in] Whether the transition to the new device power state has just been initiated or has just completed. If TRUE, the transition to the target device power state has completed. If FALSE, the power policy owner (PPO) has initiated the transition by calling the <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a> routine, but the Windows power manager has not yet issued the D<i>x</i> IRP (an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request of type <b>DevicePowerState</b>) to the device's driver stack.


### -field SystemTransition

[in] Always set to FALSE.


## -remarks


This structure is used by the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_DEVICE_POWER_STATE</a> notification. All four members of the structure contain input values that are supplied by PoFx. The PEP does not write to this structure.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>

<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>

<a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_DEVICE_POWER_STATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_DEVICE_POWER_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

