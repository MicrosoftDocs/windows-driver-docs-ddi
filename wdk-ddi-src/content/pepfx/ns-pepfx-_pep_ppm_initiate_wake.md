---
UID: NS:pepfx._PEP_PPM_INITIATE_WAKE
title: "_PEP_PPM_INITIATE_WAKE"
author: windows-driver-content
description: The PEP_PPM_INITIATE_WAKE structure indicates whether a processor requires an interrupt to wake up from an idle state.
old-location: kernel\pep_ppm_initiate_wake.htm
old-project: kernel
ms.assetid: 7627521D-4715-47D8-8268-6C9B218FFA6F
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_INITIATE_WAKE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_INITIATE_WAKE, *PPEP_PPM_INITIATE_WAKE
---

# _PEP_PPM_INITIATE_WAKE structure


## -description


The <b>PEP_PPM_INITIATE_WAKE</b> structure indicates whether a processor requires an interrupt to wake up from an idle state.


## -syntax


````
typedef struct _PEP_PPM_INITIATE_WAKE {
  BOOLEAN NeedInterruptForCompletion;
} PEP_PPM_INITIATE_WAKE, *PPEP_PPM_INITIATE_WAKE;
````


## -struct-fields




### -field NeedInterruptForCompletion

[out] Whether the processor requires an interrupt finish waking up from an idle state. Set to <b>TRUE</b> if the processor requires an interrupt, or to <b>FALSE</b> if it does not.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186809">PEP_NOTIFY_PPM_INITIATE_WAKE</a> notification. The <b>NeedInterruptForCompletion</b> member contains an output value that the platform extension plug-in (PEP) writes to the structure in response to this notification.

If the PEP sets the <b>NeedInterruptForCompletion</b> member to T<b></b>RUE, the PEP must ensure that the processor is enabled to be interrupted before the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186627">AcceptProcessorNotification</a> callback routine returns.

The PEP should set the <b>NeedInterruptForCompletion</b> member to <b>FALSE</b> if the processor is already running and/or will eventually exit the idle state (and is in the process of doing so) without requiring a software-generated interrupt.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186809">PEP_NOTIFY_PPM_INITIATE_WAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186627">AcceptProcessorNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_INITIATE_WAKE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

