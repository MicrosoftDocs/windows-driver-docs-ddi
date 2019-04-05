---
UID: NS:wdm._OB_PRE_OPERATION_PARAMETERS
title: _OB_PRE_OPERATION_PARAMETERS (wdm.h)
description: The OB_PRE_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPreCallback routine.
old-location: kernel\ob_pre_operation_parameters.htm
tech.root: kernel
ms.assetid: 211bd3b1-34ca-414d-9167-0587c90cb56a
ms.date: 04/30/2018
ms.keywords: "*POB_PRE_OPERATION_PARAMETERS, OB_PRE_OPERATION_PARAMETERS, OB_PRE_OPERATION_PARAMETERS union [Kernel-Mode Driver Architecture], POB_PRE_OPERATION_PARAMETERS, POB_PRE_OPERATION_PARAMETERS union pointer [Kernel-Mode Driver Architecture], _OB_PRE_OPERATION_PARAMETERS, kernel.ob_pre_operation_parameters, kstruct_c_328dfe5b-e8ed-4277-9003-e194abbf81ba.xml, wdm/OB_PRE_OPERATION_PARAMETERS, wdm/POB_PRE_OPERATION_PARAMETERS"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
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
- Wdm.h
api_name:
- OB_PRE_OPERATION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: OB_PRE_OPERATION_PARAMETERS, *POB_PRE_OPERATION_PARAMETERS
---

# _OB_PRE_OPERATION_PARAMETERS structure


## -description


The <b>OB_PRE_OPERATION_PARAMETERS</b> union describes the operation-specific parameters for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a> routine.


## -struct-fields




### -field CreateHandleInformation

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff558725">OB_PRE_CREATE_HANDLE_INFORMATION</a> structure that contains information that is specific to a handle that is being opened. 


### -field DuplicateHandleInformation

An <a href="https://msdn.microsoft.com/f2798729-98a2-44b6-94a6-180bb4db96cb">OB_PRE_DUPLICATE_HANDLE_INFORMATION </a> structure that contains information that is specific to a handle that is being duplicated. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558725">OB_PRE_CREATE_HANDLE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558726">OB_PRE_DUPLICATE_HANDLE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a>
 

 

