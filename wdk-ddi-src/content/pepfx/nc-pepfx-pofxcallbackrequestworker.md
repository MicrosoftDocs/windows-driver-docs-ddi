---
UID: NC:pepfx.POFXCALLBACKREQUESTWORKER
title: POFXCALLBACKREQUESTWORKER
author: windows-driver-content
description: The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.
old-location: kernel\requestworker.htm
old-project: kernel
ms.assetid: A77277D2-B644-469D-A668-78C23BF41367
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: POFXCALLBACKREQUESTWORKER, RequestWorker, RequestWorker routine [Kernel-Mode Driver Architecture], kernel.requestworker, pepfx/RequestWorker
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	RequestWorker
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# POFXCALLBACKREQUESTWORKER callback


## -description


The <b>RequestWorker</b> routine is called by a platform extension plug-in (PEP) to inform the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.


## -parameters




### -param PluginHandle [in]

A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


## -returns



None.




## -remarks



This routine is implemented by PoFx and is called by the PEP. The <b>RequestWorker</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to a <b>RequestWorker</b> routine.

Each time the PEP calls this routine, PoFx responds by sending a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification to the PEP. This notification might be delayed if a worker thread is not immediately available to process the work request.

A PEP can call this routine at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
 

 

