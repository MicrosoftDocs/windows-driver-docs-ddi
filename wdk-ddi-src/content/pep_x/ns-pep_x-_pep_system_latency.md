---
UID: NS:pep_x._PEP_SYSTEM_LATENCY
title: "_PEP_SYSTEM_LATENCY"
author: windows-driver-content
description: The PEP_SYSTEM_LATENCY structure specifies the new value for the system latency tolerance.
old-location: kernel\pep_system_latency.htm
old-project: kernel
ms.assetid: 083ACFD8-A8AE-4205-9E25-497D6A3ADBCD
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPEP_SYSTEM_LATENCY, ,, A, C, E, L, M, N, P, PEP_SYSTEM_LATENCY, PEP_SYSTEM_LATENCY structure [Kernel-Mode Driver Architecture], PPEP_SYSTEM_LATENCY, PPEP_SYSTEM_LATENCY structure pointer [Kernel-Mode Driver Architecture], S, T, Y, _, _PEP_SYSTEM_LATENCY, kernel.pep_system_latency, pepfx/PEP_SYSTEM_LATENCY, pepfx/PPEP_SYSTEM_LATENCY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_SYSTEM_LATENCY
product: Windows
targetos: Windows
req.typenames: PEP_SYSTEM_LATENCY, *PPEP_SYSTEM_LATENCY, PEP_SYSTEM_LATENCY, *PPEP_SYSTEM_LATENCY
---

# _PEP_SYSTEM_LATENCY structure


## -description


The <b>PEP_SYSTEM_LATENCY</b> structure specifies the new value for the system latency tolerance.


## -syntax


````
typedef struct _PEP_SYSTEM_LATENCY {
  ULONGLONG Latency;
} PEP_SYSTEM_LATENCY, *PPEP_SYSTEM_LATENCY;
````


## -struct-fields




### -field Latency

[in] The overall system latency tolerance, in 100-nanosecond units. This member specifies the maximum latency that the operating system can tolerate in the time required to move a component from a low-power F<i>x</i> state to F0.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186856">PEP_DPM_SYSTEM_LATENCY_UPDATE</a> notification. The <b>Latency</b> member of the structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186856">PEP_DPM_SYSTEM_LATENCY_UPDATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_SYSTEM_LATENCY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

