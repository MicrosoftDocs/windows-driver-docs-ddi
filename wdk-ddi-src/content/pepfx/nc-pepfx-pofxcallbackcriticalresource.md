---
UID: NC:pepfx.POFXCALLBACKCRITICALRESOURCE
title: POFXCALLBACKCRITICALRESOURCE
author: windows-driver-content
description: The TransitionCriticalResource routine changes the active/inactive state of a core system component.
old-location: kernel\transitioncriticalresource.htm
old-project: kernel
ms.assetid: 18CB1032-78CB-4D65-9077-02B89E9C31B4
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: POFXCALLBACKCRITICALRESOURCE, TransitionCriticalResource, TransitionCriticalResource routine [Kernel-Mode Driver Architecture], kernel.transitioncriticalresource, pepfx/TransitionCriticalResource
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
req.irql: "<= HIGH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	TransitionCriticalResource
product: Windows
targetos: Windows
req.typenames: 
---

# POFXCALLBACKCRITICALRESOURCE callback function


## -description


The <b>TransitionCriticalResource</b> routine changes the active/inactive state of a core system component.


## -parameters




### -param DeviceHandle [in]

A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


### -param Component [in]

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Active [in]

Whether to transition the device from inactive to active, or vice versa. Set to TRUE to transition the device from inactive to active, or to FALSE to transition the device from active to inactive.


## -returns



None




## -remarks



This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>TransitionCriticalResource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>TransitionCriticalResource</b> routine.

A PEP can call this routine at IRQL &lt;= HIGH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
 

 

