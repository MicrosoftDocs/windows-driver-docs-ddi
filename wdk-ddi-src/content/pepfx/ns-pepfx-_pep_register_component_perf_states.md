---
UID: NS:pepfx._PEP_REGISTER_COMPONENT_PERF_STATES
title: _PEP_REGISTER_COMPONENT_PERF_STATES (pepfx.h)
description: The PEP_REGISTER_COMPONENT_PERF_STATES structure describes the performance states (P-states) of the specified component.
old-location: kernel\pep_register_component_perf_states.htm
tech.root: kernel
ms.assetid: 063ADC0A-3455-4966-A11C-BDD5BA08A685
ms.date: 04/30/2018
keywords: ["PEP_REGISTER_COMPONENT_PERF_STATES structure"]
ms.keywords: "*PPEP_REGISTER_COMPONENT_PERF_STATES, PEP_REGISTER_COMPONENT_PERF_STATES, PEP_REGISTER_COMPONENT_PERF_STATES structure [Kernel-Mode Driver Architecture], PPEP_REGISTER_COMPONENT_PERF_STATES, PPEP_REGISTER_COMPONENT_PERF_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_COMPONENT_PERF_STATES, kernel.pep_register_component_perf_states, pepfx/PEP_REGISTER_COMPONENT_PERF_STATES, pepfx/PPEP_REGISTER_COMPONENT_PERF_STATES"
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
targetos: Windows
req.typenames: PEP_REGISTER_COMPONENT_PERF_STATES, *PPEP_REGISTER_COMPONENT_PERF_STATES
f1_keywords:
 - _PEP_REGISTER_COMPONENT_PERF_STATES
 - pepfx/_PEP_REGISTER_COMPONENT_PERF_STATES
 - PPEP_REGISTER_COMPONENT_PERF_STATES
 - pepfx/PPEP_REGISTER_COMPONENT_PERF_STATES
 - PEP_REGISTER_COMPONENT_PERF_STATES
 - pepfx/PEP_REGISTER_COMPONENT_PERF_STATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_REGISTER_COMPONENT_PERF_STATES
---

# _PEP_REGISTER_COMPONENT_PERF_STATES structure


## -description

The <b>PEP_REGISTER_COMPONENT_PERF_STATES</b> structure describes the performance states (P-states) of the specified component.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -field Flags

[in] A set of input flags. No flag bits are currently defined for this member, which is always zero.

### -field PerfStateInfo

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a> structure that contains the performance information for this component's P-states. If this member is non-NULL, it points to P-state information that was supplied by the device driver.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a> notification. The values of all members of the <b>PEP_REGISTER_COMPONENT_PERF_STATES</b> structure  are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) when the notification is sent. The PEP must not write to this structure.

If the <b>PerfStateInfo</b> member is not NULL, the device driver has provided P-state information and requires the PEP to use it.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>

