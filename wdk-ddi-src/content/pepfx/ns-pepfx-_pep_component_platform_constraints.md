---
UID: NS:pepfx._PEP_COMPONENT_PLATFORM_CONSTRAINTS
title: "_PEP_COMPONENT_PLATFORM_CONSTRAINTS"
description: The PEP_COMPONENT_PLATFORM_CONSTRAINTS structure describes the lowest-powered Fx state of that a component can be in when the platform is in a particular idle state.
old-location: kernel\pep_component_platform_constraints.htm
tech.root: kernel
ms.assetid: F7C2DFCC-DB74-4E2E-B252-4897FA320C03
ms.date: 01/11/2019
ms.keywords: "*PPEP_COMPONENT_PLATFORM_CONSTRAINTS, PEP_COMPONENT_PLATFORM_CONSTRAINTS, PEP_COMPONENT_PLATFORM_CONSTRAINTS structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PLATFORM_CONSTRAINTS, PPEP_COMPONENT_PLATFORM_CONSTRAINTS structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PLATFORM_CONSTRAINTS, kernel.pep_component_platform_constraints, pepfx/PEP_COMPONENT_PLATFORM_CONSTRAINTS, pepfx/PPEP_COMPONENT_PLATFORM_CONSTRAINTS"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_COMPONENT_PLATFORM_CONSTRAINTS
product:
- Windows
targetos: Windows
req.typenames: PEP_COMPONENT_PLATFORM_CONSTRAINTS, *PPEP_COMPONENT_PLATFORM_CONSTRAINTS
---

# _PEP_COMPONENT_PLATFORM_CONSTRAINTS structure

## -description

The **PEP_COMPONENT_PLATFORM_CONSTRAINTS** structure describes the lowest-powered F*x* state of that a component can be in when the platform is in a particular idle state.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The platform extension plug-in (PEP) supplied this handle in response to a previous [PEP_DPM_REGISTER_DEVICE](ns-pepfx-_pep_register_crashdump_device.md) notification.

### -field Component

[in] The index that identifies the component. This member is an index into the **Components** array in the [PEP_DEVICE_REGISTER_V2](ns-pepfx-_pep_device_register_v2.md) structure that the PEP previously supplied in response to the **PEP_DPM_REGISTER_DEVICE** notification for this device. If the **Components** array contains N elements, component indexes range from 0 to N–1.

### -field MinimumFStates

[in] A pointer to an output buffer. The PEP writes a ULONG array to this buffer that specifies the lowest-powered F*x* state that  the component can be in for each platform idle state. An element with a value of 0 indicates F0, a value of 1 indicates F1, and so on. If the platform supports M idle states, array elements 0 to M–1 specify the F*x* states corresponding to platform idle states 0 to M–1.

### -field PlatformStateCount

[in] The number of elements in the **MinimumFStates** array. The array contains one element for each platform idle state. The Windows [power management framework (PoFx)](https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) previously sent a [PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES](ns-pepfx-_pep_ppm_query_platform_states) notification to the PEP to determine the number of supported platform idle states.

## -remarks

This structure is used by the [PEP_DPM_COMPONENT_IDLE_CONSTRAINTS](https://docs.microsoft.com/windows-hardware/drivers/kernel/dpm-notifications#pep_dpm_component_idle_constraints) notification. All four members of the structure contain input values that PoFx supplies when this notification is sent. PoFx allocates the buffer pointed to by the **MinimumFStates** member, and the PEP writes to this buffer in response to the notification.

## -see-also

[PEP_DEVICE_REGISTER_V2](ns-pepfx-_pep_device_register_v2.md)

[PEP_DPM_COMPONENT_IDLE_CONSTRAINTS](https://docs.microsoft.com/windows-hardware/drivers/kernel/dpm-notifications#pep_dpm_component_idle_constraints)

[PEP_DPM_REGISTER_DEVICE](https://docs.microsoft.com/windows-hardware/drivers/kernel/dpm-notifications#pep_dpm_register_device)

[PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES](ns-pepfx-_pep_ppm_query_platform_states)
