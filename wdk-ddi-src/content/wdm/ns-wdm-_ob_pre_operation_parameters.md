---
UID: NS:wdm._OB_PRE_OPERATION_PARAMETERS
title: "_OB_PRE_OPERATION_PARAMETERS"
author: windows-driver-content
description: The OB_PRE_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPreCallback routine.
old-location: kernel\ob_pre_operation_parameters.htm
old-project: kernel
ms.assetid: 211bd3b1-34ca-414d-9167-0587c90cb56a
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*POB_PRE_OPERATION_PARAMETERS, OB_PRE_OPERATION_PARAMETERS, OB_PRE_OPERATION_PARAMETERS union [Kernel-Mode Driver Architecture], POB_PRE_OPERATION_PARAMETERS, POB_PRE_OPERATION_PARAMETERS union pointer [Kernel-Mode Driver Architecture], _OB_PRE_OPERATION_PARAMETERS, kernel.ob_pre_operation_parameters, kstruct_c_328dfe5b-e8ed-4277-9003-e194abbf81ba.xml, wdm/OB_PRE_OPERATION_PARAMETERS, wdm/POB_PRE_OPERATION_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	OB_PRE_OPERATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: OB_PRE_OPERATION_PARAMETERS, *POB_PRE_OPERATION_PARAMETERS
req.product: Windows 10 or later.
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_PRE_OPERATION_PARAMETERS union%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

