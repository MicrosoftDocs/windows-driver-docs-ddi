---
UID: NS:pep_x._PEP_PPM_IDLE_CANCEL
title: _PEP_PPM_IDLE_CANCEL (pep_x.h)
description: The PEP_PPM_IDLE_CANCEL structure indicates why the processor could not enter the previously selected idle state.
old-location: kernel\pep_ppm_idle_cancel.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_IDLE_CANCEL structure"]
ms.keywords: "*PPEP_PPM_IDLE_CANCEL, PEP_PPM_IDLE_CANCEL, PEP_PPM_IDLE_CANCEL structure [Kernel-Mode Driver Architecture], PPEP_PPM_IDLE_CANCEL, PPEP_PPM_IDLE_CANCEL structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_IDLE_CANCEL, kernel.pep_ppm_idle_cancel, pep_x/PEP_PPM_IDLE_CANCEL, pep_x/PPEP_PPM_IDLE_CANCEL"
req.header: pep_x.h
req.include-header: Pepfx.h
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
req.typenames: PEP_PPM_IDLE_CANCEL, *PPEP_PPM_IDLE_CANCEL
f1_keywords:
 - _PEP_PPM_IDLE_CANCEL
 - pep_x/_PEP_PPM_IDLE_CANCEL
 - PPEP_PPM_IDLE_CANCEL
 - pep_x/PPEP_PPM_IDLE_CANCEL
 - PEP_PPM_IDLE_CANCEL
 - pep_x/PEP_PPM_IDLE_CANCEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pep_x.h
api_name:
 - _PEP_PPM_IDLE_CANCEL
 - PPEP_PPM_IDLE_CANCEL
 - PEP_PPM_IDLE_CANCEL
---

# _PEP_PPM_IDLE_CANCEL structure


## -description

The <b>PEP_PPM_IDLE_CANCEL</b> structure indicates why the processor could not enter the previously selected idle state.

## -struct-fields

### -field CancelCode [in]

A <a href="/windows-hardware/drivers/ddi/pep_x/ne-pep_x-pep_processor_idle_cancel_code">PEP_PROCESSOR_IDLE_CANCEL_CODE</a> enumeration value that indicates why the processor could not enter the idle state selected by the platform extension plug-in (PEP).

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_idle_cancel">PEP_NOTIFY_PPM_IDLE_CANCEL</a> notification. The <b>CancelCode</b> member of the structure contains an input value that the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx) supplies before this notification is sent.

## -see-also

<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_idle_cancel">PEP_NOTIFY_PPM_IDLE_CANCEL</a>



<a href="/windows-hardware/drivers/ddi/pep_x/ne-pep_x-pep_processor_idle_cancel_code">PEP_PROCESSOR_IDLE_CANCEL_CODE</a>

