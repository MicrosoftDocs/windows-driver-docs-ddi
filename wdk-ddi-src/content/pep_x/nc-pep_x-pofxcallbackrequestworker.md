---
UID: NC:pep_x.POFXCALLBACKREQUESTWORKER
title: POFXCALLBACKREQUESTWORKER
author: windows-driver-content
description: The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.
old-location: kernel\requestworker.htm
old-project: kernel
ms.assetid: A77277D2-B644-469D-A668-78C23BF41367
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.requestworker, RequestWorker, RequestWorker routine [Kernel-Mode Driver Architecture], RequestWorker, POFXCALLBACKREQUESTWORKER, POFXCALLBACKREQUESTWORKER, pepfx/RequestWorker
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	pepfx.h
apiname:
-	RequestWorker
product: Windows
targetos: Windows
req.typenames: "*PPO_FX_CORE_DEVICE, PO_FX_CORE_DEVICE"
---

# POFXCALLBACKREQUESTWORKER callback


## -description


The <b>RequestWorker</b> routine is called by a platform extension plug-in (PEP) to inform the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.


## -prototype


````
POFXCALLBACKREQUESTWORKER RequestWorker;

VOID RequestWorker(
  _In_ POHANDLE PluginHandle
)
{ ... }
````


## -parameters




### -param PluginHandle [in]

A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


## -returns



None.




## -remarks



This routine is implemented by PoFx and is called by the PEP. The <b>RequestWorker</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to a <b>RequestWorker</b> routine.

Each time the PEP calls this routine, PoFx responds by sending a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification to the PEP. This notification might be delayed if a worker thread is not immediately available to process the work request.

A PEP can call this routine at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKREQUESTWORKER routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

