---
UID: NS:pepfx._PEP_PPM_IS_PROCESSOR_HALTED
title: "_PEP_PPM_IS_PROCESSOR_HALTED"
author: windows-driver-content
description: The PEP_PPM_IS_PROCESSOR_HALTED structure indicates whether the processor is currently halted in its selected idle state.
old-location: kernel\pep_ppm_is_processor_halted.htm
old-project: kernel
ms.assetid: 284BAFE1-C632-428D-800C-60C538052C02
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_PPM_IS_PROCESSOR_HALTED, _PEP_PPM_IS_PROCESSOR_HALTED, pepfx/PEP_PPM_IS_PROCESSOR_HALTED, PPEP_PPM_IS_PROCESSOR_HALTED structure pointer [Kernel-Mode Driver Architecture], *PPEP_PPM_IS_PROCESSOR_HALTED, kernel.pep_ppm_is_processor_halted, PPEP_PPM_IS_PROCESSOR_HALTED, pepfx/PPEP_PPM_IS_PROCESSOR_HALTED, PEP_PPM_IS_PROCESSOR_HALTED structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
-	PEP_PPM_IS_PROCESSOR_HALTED
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_IS_PROCESSOR_HALTED, PEP_PPM_IS_PROCESSOR_HALTED"
---

# _PEP_PPM_IS_PROCESSOR_HALTED structure


## -description


The <b>PEP_PPM_IS_PROCESSOR_HALTED</b> structure indicates whether the processor is currently halted in its selected idle state.


## -syntax


````
typedef struct _PEP_PPM_IS_PROCESSOR_HALTED {
  BOOLEAN Halted;
} PEP_PPM_IS_PROCESSOR_HALTED, *PPEP_PPM_IS_PROCESSOR_HALTED;
````


## -struct-fields




### -field Halted

[out] Whether the processor is halted. Set to <b>TRUE</b> if the processor is halted, or to <b>FALSE</b> if it is not halted.


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186810">PEP_NOTIFY_PPM_IS_PROCESSOR_HALTED</a> notification. The <b>Halted</b> member contains an output value that the platform extension plug-in (PEP) writes to the structure in response to this notification.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186810">PEP_NOTIFY_PPM_IS_PROCESSOR_HALTED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_IS_PROCESSOR_HALTED structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

