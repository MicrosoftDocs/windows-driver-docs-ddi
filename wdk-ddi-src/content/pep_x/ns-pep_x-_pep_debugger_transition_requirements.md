---
UID: NS:pep_x._PEP_DEBUGGER_TRANSITION_REQUIREMENTS
title: _PEP_DEBUGGER_TRANSITION_REQUIREMENTS (pep_x.h)
description: The PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure indicates the platform idle states for which the debugger device must be turned on.
old-location: kernel\pep_debugger_transition_requirements.htm
tech.root: kernel
ms.assetid: 5DF830CA-ECC3-404A-AA5F-3DB487BC85B3
ms.date: 04/30/2018
keywords: ["PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure"]
ms.keywords: "*PPEP_DEBUGGER_TRANSITION_REQUIREMENTS, PEP_DEBUGGER_TRANSITION_REQUIREMENTS, PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure [Kernel-Mode Driver Architecture], PPEP_DEBUGGER_TRANSITION_REQUIREMENTS, PPEP_DEBUGGER_TRANSITION_REQUIREMENTS structure pointer [Kernel-Mode Driver Architecture], _PEP_DEBUGGER_TRANSITION_REQUIREMENTS, kernel.pep_debugger_transition_requirements, pepfx/PEP_DEBUGGER_TRANSITION_REQUIREMENTS, pepfx/PPEP_DEBUGGER_TRANSITION_REQUIREMENTS"
req.header: pep_x.h
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
req.typenames: PEP_DEBUGGER_TRANSITION_REQUIREMENTS, *PPEP_DEBUGGER_TRANSITION_REQUIREMENTS
f1_keywords:
 - _PEP_DEBUGGER_TRANSITION_REQUIREMENTS
 - pep_x/_PEP_DEBUGGER_TRANSITION_REQUIREMENTS
 - PPEP_DEBUGGER_TRANSITION_REQUIREMENTS
 - pep_x/PPEP_DEBUGGER_TRANSITION_REQUIREMENTS
 - PEP_DEBUGGER_TRANSITION_REQUIREMENTS
 - pep_x/PEP_DEBUGGER_TRANSITION_REQUIREMENTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_DEBUGGER_TRANSITION_REQUIREMENTS
---

# _PEP_DEBUGGER_TRANSITION_REQUIREMENTS structure (pep_x.h)


## -description

The <b>PEP_DEBUGGER_TRANSITION_REQUIREMENTS</b> structure indicates the platform idle states for which the debugger device must be turned on.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the debugger device. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

### -field PlatformStateCount

[in] The number of entries in the array pointed to by the <b>PowerTransitionRequired</b> member. This number is the same as the number of supported platform idle states that the PEP specified in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.

### -field PowerTransitionRequired

[in] An output buffer to which the PEP writes a BOOLEAN array that indicates the platform idle states for which power to the debugger device must be turned on. This buffer is allocated by the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) and is guaranteed to be large enough to contain the number of array elements specified by the <b>PlatformStateCount</b> member. Set an array element to TRUE if the debugger device must be turned on in the corresponding platform idle state. Set to FALSE to indicate that the device is not required to be turned on in this state. If the platform supports N idle states, the array contains N elements, and idle states are numbered 0 to N–1 in the order in which they are represented in the array.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_debugger_transition_requirements">PEP_DPM_QUERY_DEBUGGER_TRANSITION_REQUIREMENTS</a> notification. All three members of the structure contain input values that are supplied by PoFx when this notification is sent to the PEP.

During a debugging session, the debugger component that runs on the target computer communicates with the host computer through a debugger device such as a USB host controller, UART, or networking device.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_debugger_transition_requirements">PEP_DPM_QUERY_DEBUGGER_TRANSITION_REQUIREMENTS</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>