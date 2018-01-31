---
UID: NS:pep_x._PEP_PPM_IDLE_CANCEL
title: "_PEP_PPM_IDLE_CANCEL"
author: windows-driver-content
description: The PEP_PPM_IDLE_CANCEL structure indicates why the processor could not enter the previously selected idle state.
old-location: kernel\pep_ppm_idle_cancel.htm
old-project: kernel
ms.assetid: 29B16A23-A3C1-4994-8F72-403BE32ABBD2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PPM_IDLE_CANCEL structure pointer [Kernel-Mode Driver Architecture], pep_x/PPEP_PPM_IDLE_CANCEL, pep_x/PEP_PPM_IDLE_CANCEL, _PEP_PPM_IDLE_CANCEL, *PPEP_PPM_IDLE_CANCEL, PEP_PPM_IDLE_CANCEL, PEP_PPM_IDLE_CANCEL structure [Kernel-Mode Driver Architecture], PPEP_PPM_IDLE_CANCEL, kernel.pep_ppm_idle_cancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pep_x.h
apiname:
-	PEP_PPM_IDLE_CANCEL
product: Windows
targetos: Windows
req.typenames: PEP_PPM_IDLE_CANCEL, *PPEP_PPM_IDLE_CANCEL
---

# _PEP_PPM_IDLE_CANCEL structure


## -description


The <b>PEP_PPM_IDLE_CANCEL</b> structure indicates why the processor could not enter the previously selected idle state.


## -syntax


````
typedef struct _PEP_PPM_IDLE_CANCEL {
  PEP_PROCESSOR_IDLE_CANCEL_CODE CancelCode;
} PEP_PPM_IDLE_CANCEL, *PPEP_PPM_IDLE_CANCEL;
````


## -struct-fields




#### - CancelCode

[in] A <a href="..\pep_x\ne-pep_x-ppep_processor_idle_cancel_code.md">PEP_PROCESSOR_IDLE_CANCEL_CODE</a> enumeration value that indicates why the processor could not enter the idle state selected by the platform extension plug-in (PEP).


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629119">PEP_NOTIFY_PPM_IDLE_CANCEL</a> notification. The <b>CancelCode</b> member of the structure contains an input value that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) supplies before this notification is sent.



## -see-also

<a href="..\pep_x\ne-pep_x-ppep_processor_idle_cancel_code.md">PEP_PROCESSOR_IDLE_CANCEL_CODE</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629119">PEP_NOTIFY_PPM_IDLE_CANCEL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_IDLE_CANCEL structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

