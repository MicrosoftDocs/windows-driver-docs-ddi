---
UID: NS:pepfx._PEP_WORK_COMPLETE_IDLE_STATE
title: _PEP_WORK_COMPLETE_IDLE_STATE (pepfx.h)
description: The PEP_WORK_COMPLETE_IDLE_STATE structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new Fx power state.
old-location: kernel\pep_work_complete_idle_state.htm
tech.root: kernel
ms.assetid: 6065A77F-5E80-4D3D-8EF1-4D336505122A
ms.date: 04/30/2018
keywords: ["PEP_WORK_COMPLETE_IDLE_STATE structure"]
ms.keywords: "*PPEP_WORK_COMPLETE_IDLE_STATE, PEP_WORK_COMPLETE_IDLE_STATE, PEP_WORK_COMPLETE_IDLE_STATE structure [Kernel-Mode Driver Architecture], PPEP_WORK_COMPLETE_IDLE_STATE, PPEP_WORK_COMPLETE_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_COMPLETE_IDLE_STATE, kernel.pep_work_complete_idle_state, pepfx/PEP_WORK_COMPLETE_IDLE_STATE, pepfx/PPEP_WORK_COMPLETE_IDLE_STATE"
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
req.typenames: PEP_WORK_COMPLETE_IDLE_STATE, *PPEP_WORK_COMPLETE_IDLE_STATE
f1_keywords:
 - _PEP_WORK_COMPLETE_IDLE_STATE
 - pepfx/_PEP_WORK_COMPLETE_IDLE_STATE
 - PPEP_WORK_COMPLETE_IDLE_STATE
 - pepfx/PPEP_WORK_COMPLETE_IDLE_STATE
 - PEP_WORK_COMPLETE_IDLE_STATE
 - pepfx/PEP_WORK_COMPLETE_IDLE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_WORK_COMPLETE_IDLE_STATE
---

# _PEP_WORK_COMPLETE_IDLE_STATE structure (pepfx.h)


## -description

The <b>PEP_WORK_COMPLETE_IDLE_STATE</b> structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new F<i>x</i> power state.

## -struct-fields

### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.

### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

## -remarks

The <b>CompleteIdleState</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_COMPLETE_IDLE_STATE</b> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>

