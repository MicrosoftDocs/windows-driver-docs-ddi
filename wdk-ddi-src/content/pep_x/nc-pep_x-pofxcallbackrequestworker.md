---
UID: NC:pep_x.POFXCALLBACKREQUESTWORKER
title: POFXCALLBACKREQUESTWORKER (pep_x.h)
description: The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.
old-location: kernel\requestworker.htm
tech.root: kernel
ms.assetid: A77277D2-B644-469D-A668-78C23BF41367
ms.date: 04/30/2018
ms.keywords: POFXCALLBACKREQUESTWORKER, RequestWorker, RequestWorker routine [Kernel-Mode Driver Architecture], kernel.requestworker, pepfx/RequestWorker
ms.topic: callback
f1_keywords:
 - "pep_x/RequestWorker"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- pepfx.h
api_name:
- RequestWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# POFXCALLBACKREQUESTWORKER callback function


## -description


The <b>RequestWorker</b> routine is called by a platform extension plug-in (PEP) to inform the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.


## -parameters




### -param PluginHandle [in]

A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


## -returns



None.




## -remarks



This routine is implemented by PoFx and is called by the PEP. The <b>RequestWorker</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to a <b>RequestWorker</b> routine.

Each time the PEP calls this routine, PoFx responds by sending a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification to the PEP. This notification might be delayed if a worker thread is not immediately available to process the work request.

A PEP can call this routine at IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
 

 

