---
UID: NE:pep_x.__unnamed_enum_1
title: PEP_PROCESSOR_IDLE_CANCEL_CODE (pep_x.h)
description: The PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration values indicate reasons why a processor cannot enter an idle state that was previously selected by the platform extension plug-in (PEP).
old-location: kernel\pep_processor_idle_cancel_code.htm
tech.root: kernel
ms.assetid: 6112360C-B74F-4A77-8DE5-3EF1AAF49533
ms.date: 04/30/2018
ms.keywords: "*PPEP_PROCESSOR_IDLE_CANCEL_CODE, PEP_PROCESSOR_IDLE_CANCEL_CODE, PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration [Kernel-Mode Driver Architecture], PepIdleCancelDependencyCheckFailed, PepIdleCancelMax, PepIdleCancelNoCState, PepIdleCancelWorkPending, kernel.pep_processor_idle_cancel_code, pep_x/PEP_PROCESSOR_IDLE_CANCEL_CODE, pep_x/PepIdleCancelDependencyCheckFailed, pep_x/PepIdleCancelMax, pep_x/PepIdleCancelNoCState, pep_x/PepIdleCancelWorkPending"
f1_keywords:
 - "pep_x/PEP_PROCESSOR_IDLE_CANCEL_CODE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pep_x.h
api_name:
- PEP_PROCESSOR_IDLE_CANCEL_CODE
product:
- Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_CANCEL_CODE, *PPEP_PROCESSOR_IDLE_CANCEL_CODE
---

# PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration


## -description


The <b>PEP_PROCESSOR_IDLE_CANCEL_CODE</b> enumeration values indicate reasons why a processor cannot enter an idle state that was previously selected by the platform extension plug-in (PEP).


## -enum-fields




### -field PepIdleCancelWorkPending

The processor has pending work that prevents it from entering the selected idle state.


### -field PepIdleCancelDependencyCheckFailed

The processor can enter the selected idle state only after one or more secondary processors have entered their corresponding idle states, but not all of these secondary processors have entered the correct idle states.


### -field PepIdleCancelNoCState

The selected idle state corresponds to a C-state that is not supported. The PEP previously received a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_cst_states">PEP_NOTIFY_PPM_CST_STATES</a> notification that supplied a list of the supported C-states for this processor.


### -field PepIdleCancelMax

Reserved for use by the operating system.


## -remarks



The <b>CancelCode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_idle_cancel">PEP_PPM_IDLE_CANCEL</a> structure contains a <b>PEP_PROCESSOR_IDLE_CANCEL_CODE</b> enumeration value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_cst_states">PEP_NOTIFY_PPM_CST_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_idle_cancel">PEP_PPM_IDLE_CANCEL</a>
 

 

