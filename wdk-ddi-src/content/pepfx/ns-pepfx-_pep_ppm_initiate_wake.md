---
UID: NS:pepfx._PEP_PPM_INITIATE_WAKE
title: "_PEP_PPM_INITIATE_WAKE"
author: windows-driver-content
description: The PEP_PPM_INITIATE_WAKE structure indicates whether a processor requires an interrupt to wake up from an idle state.
old-location: kernel\pep_ppm_initiate_wake.htm
old-project: kernel
ms.assetid: 7627521D-4715-47D8-8268-6C9B218FFA6F
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_INITIATE_WAKE, PEP_PPM_INITIATE_WAKE, PEP_PPM_INITIATE_WAKE structure [Kernel-Mode Driver Architecture], PPEP_PPM_INITIATE_WAKE, PPEP_PPM_INITIATE_WAKE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_INITIATE_WAKE, kernel.pep_ppm_initiate_wake, pepfx/PEP_PPM_INITIATE_WAKE, pepfx/PPEP_PPM_INITIATE_WAKE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_INITIATE_WAKE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_INITIATE_WAKE, *PPEP_PPM_INITIATE_WAKE
---

# _PEP_PPM_INITIATE_WAKE structure


## -description


The <b>PEP_PPM_INITIATE_WAKE</b> structure indicates whether a processor requires an interrupt to wake up from an idle state.


## -struct-fields




### -field NeedInterruptForCompletion

[out] Whether the processor requires an interrupt finish waking up from an idle state. Set to <b>TRUE</b> if the processor requires an interrupt, or to <b>FALSE</b> if it does not.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186809">PEP_NOTIFY_PPM_INITIATE_WAKE</a> notification. The <b>NeedInterruptForCompletion</b> member contains an output value that the platform extension plug-in (PEP) writes to the structure in response to this notification.

If the PEP sets the <b>NeedInterruptForCompletion</b> member to T<b></b>RUE, the PEP must ensure that the processor is enabled to be interrupted before the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186627">AcceptProcessorNotification</a> callback routine returns.

The PEP should set the <b>NeedInterruptForCompletion</b> member to <b>FALSE</b> if the processor is already running and/or will eventually exit the idle state (and is in the process of doing so) without requiring a software-generated interrupt.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186627">AcceptProcessorNotification</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186809">PEP_NOTIFY_PPM_INITIATE_WAKE</a>
 

 

