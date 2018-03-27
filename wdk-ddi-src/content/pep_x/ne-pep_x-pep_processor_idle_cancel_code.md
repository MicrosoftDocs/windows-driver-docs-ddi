---
UID: NE:pep_x.PEP_PROCESSOR_IDLE_CANCEL_CODE
title: PEP_PROCESSOR_IDLE_CANCEL_CODE
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration values indicate reasons why a processor cannot enter an idle state that was previously selected by the platform extension plug-in (PEP).
old-location: kernel\pep_processor_idle_cancel_code.htm
old-project: kernel
ms.assetid: 6112360C-B74F-4A77-8DE5-3EF1AAF49533
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PROCESSOR_IDLE_CANCEL_CODE, PEP_PROCESSOR_IDLE_CANCEL_CODE, PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration [Kernel-Mode Driver Architecture], PepIdleCancelDependencyCheckFailed, PepIdleCancelMax, PepIdleCancelNoCState, PepIdleCancelWorkPending, kernel.pep_processor_idle_cancel_code, pep_x/PEP_PROCESSOR_IDLE_CANCEL_CODE, pep_x/PepIdleCancelDependencyCheckFailed, pep_x/PepIdleCancelMax, pep_x/PepIdleCancelNoCState, pep_x/PepIdleCancelWorkPending"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pep_x.h
api_name:
-	PEP_PROCESSOR_IDLE_CANCEL_CODE
product: Windows
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

The selected idle state corresponds to a C-state that is not supported. The PEP previously received a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a> notification that supplied a list of the supported C-states for this processor.


### -field PepIdleCancelMax

Reserved for use by the operating system.


## -remarks



The <b>CancelCode</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt629119">PEP_PPM_IDLE_CANCEL</a> structure contains a <b>PEP_PROCESSOR_IDLE_CANCEL_CODE</b> enumeration value.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629119">PEP_PPM_IDLE_CANCEL</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_CANCEL_CODE enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

