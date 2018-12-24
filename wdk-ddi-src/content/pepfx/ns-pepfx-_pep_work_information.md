---
UID: NS:pepfx._PEP_WORK_INFORMATION
title: "_PEP_WORK_INFORMATION"
description: The PEP_WORK_INFORMATION structure describes a work item that the PEP is submitting to the Windows power management framework (PoFx).
old-location: kernel\pep_work_information.htm
tech.root: kernel
ms.assetid: 7A3B2A94-AE6F-4DCC-9CDF-E2D5799C9F0D
ms.date: 04/30/2018
ms.keywords: "*PPEP_WORK_INFORMATION, PEP_WORK_INFORMATION, PEP_WORK_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_WORK_INFORMATION, PPEP_WORK_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_INFORMATION, kernel.pep_work_information, pepfx/PEP_WORK_INFORMATION, pepfx/PPEP_WORK_INFORMATION"
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
-	PEP_WORK_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PEP_WORK_INFORMATION, *PPEP_WORK_INFORMATION
---

# _PEP_WORK_INFORMATION structure


## -description


The <b>PEP_WORK_INFORMATION</b> structure describes a work item that the PEP is submitting to the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).


## -struct-fields




### -field WorkType

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186866">PEP_WORK_TYPE</a> enumeration value. This member indicates the type of work requested by the PEP, which also determines the type of structure that is contained in the unnamed union in the <b>PEP_WORK_INFORMATION</b> structure.


### -field PowerControl

 


### -field CompleteIdleState

 


### -field CompletePerfState

 


### -field AcpiNotify

 


### -field ControlMethodComplete

 




#### - ( unnamed union )

The data structure that is associated with the type of work specified by the <b>WorkType</b> member.



#### PowerControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186865">PEP_WORK_POWER_CONTROL</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkRequestPowerControl</b>.



#### CompleteIdleState

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186862">PEP_WORK_COMPLETE_IDLE_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompleteIdleState</b>.



#### CompletePerfState

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186863">PEP_WORK_COMPLETE_PERF_STATE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkCompletePerfState</b>.



#### AcpiNotify

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186861">PEP_WORK_ACPI_NOTIFY</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiNotify</b>.



#### ControlMethodComplete

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186860">PEP_WORK_ACPI_EVALUATE_CONTROL_METHOD_COMPLETE</a> structure. This structure is used if <b>WorkType</b> = <b>PepWorkAcpiEvaluateControlMethodComplete</b>.


## -remarks



The <b>WorkInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186859">PEP_WORK</a> structure is a pointer to a <b>PEP_WORK_INFORMATION</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186859">PEP_WORK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186861">PEP_WORK_ACPI_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629128">PEP_WORK_ACTIVE_COMPLETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186862">PEP_WORK_COMPLETE_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186863">PEP_WORK_COMPLETE_PERF_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629129">PEP_WORK_DEVICE_IDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629130">PEP_WORK_DEVICE_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629131">PEP_WORK_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186865">PEP_WORK_POWER_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186866">PEP_WORK_TYPE</a>
 

 

