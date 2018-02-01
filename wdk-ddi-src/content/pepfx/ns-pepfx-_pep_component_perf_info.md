---
UID: NS:pepfx._PEP_COMPONENT_PERF_INFO
title: "_PEP_COMPONENT_PERF_INFO"
author: windows-driver-content
description: The PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component.
old-location: kernel\pep_component_perf_info.htm
old-project: kernel
ms.assetid: F05D67A0-6583-4C3E-B9AA-B99381A18047
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PPEP_COMPONENT_PERF_INFO, PPEP_COMPONENT_PERF_INFO, kernel.pep_component_perf_info, PEP_COMPONENT_PERF_INFO structure [Kernel-Mode Driver Architecture], PEP_COMPONENT_PERF_INFO, PPEP_COMPONENT_PERF_INFO structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PERF_INFO, pepfx/PPEP_COMPONENT_PERF_INFO, pepfx/PEP_COMPONENT_PERF_INFO"
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
-	PEP_COMPONENT_PERF_INFO
product: Windows
targetos: Windows
req.typenames: "*PPEP_COMPONENT_PERF_INFO, PEP_COMPONENT_PERF_INFO"
---

# _PEP_COMPONENT_PERF_INFO structure


## -description


The <b>PEP_COMPONENT_PERF_INFO</b> structure describes the performance states (P-states) of a component.


## -syntax


````
typedef struct _PEP_COMPONENT_PERF_INFO {
  ULONG                  SetCount;
  PEP_COMPONENT_PERF_SET PerfStateSets[ANYSIZE_ARRAY];
} PEP_COMPONENT_PERF_INFO, *PPEP_COMPONENT_PERF_INFO;
````


## -struct-fields




### -field SetCount

The number of elements in the <b>PerfStateSets</b> array.


### -field PerfStateSets

The first element in an array of <a href="..\pepfx\ns-pepfx-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a> structures. Each array element describes a P-state of the component. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_COMPONENT_PERF_INFO</b> structure.


## -remarks


This structure is used in conjunction with the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186848">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a> notification. The <b>PerfStateSets</b> member of the <a href="..\pepfx\ns-pepfx-_pep_register_component_perf_states.md">PEP_REGISTER_COMPONENT_PERF_STATES</a> structure is a <b>PEP_COMPONENT_PERF_INFO</b> structure.

The <b>PEP_COMPONENT_PERF_INFO</b> structure contains input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The platform extension plug-in (PEP) must not write to this structure.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186848">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a>

<a href="..\pepfx\ns-pepfx-_pep_component_perf_info.md">PEP_COMPONENT_PERF_INFO</a>

<a href="..\pepfx\ns-pepfx-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a>

<a href="..\pepfx\ns-pepfx-_pep_register_component_perf_states.md">PEP_REGISTER_COMPONENT_PERF_STATES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COMPONENT_PERF_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

