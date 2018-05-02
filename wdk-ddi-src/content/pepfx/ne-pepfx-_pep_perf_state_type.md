---
UID: NE:pepfx._PEP_PERF_STATE_TYPE
title: "_PEP_PERF_STATE_TYPE"
author: windows-driver-content
description: The PEP_PERF_STATE_TYPE enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component.
old-location: kernel\pep_perf_state_type.htm
old-project: kernel
ms.assetid: 8DF40988-995E-4C37-8864-0C405DE885C9
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_PERF_STATE_TYPE, PEP_PERF_STATE_TYPE, PEP_PERF_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PepPerfStateTypeDiscrete, PepPerfStateTypeMax, PepPerfStateTypeRange, _PEP_PERF_STATE_TYPE, kernel.pep_perf_state_type, pepfx/PEP_PERF_STATE_TYPE, pepfx/PepPerfStateTypeDiscrete, pepfx/PepPerfStateTypeMax, pepfx/PepPerfStateTypeRange"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PERF_STATE_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_PERF_STATE_TYPE, *PPEP_PERF_STATE_TYPE
---

# _PEP_PERF_STATE_TYPE enumeration


## -description


The <b>PEP_PERF_STATE_TYPE</b> enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component.


## -enum-fields




### -field PepPerfStateTypeDiscrete

The performance information is specified as a set of discrete values.


### -field PepPerfStateTypeRange

The performance information is specified as a range of values.


### -field PepPerfStateTypeMax

Reserved for use by operating system.


## -remarks



The <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186702">PEP_COMPONENT_PERF_SET</a> structure is a <b>PEP_PERF_STATE_TYPE</b> enumeration value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186702">PEP_COMPONENT_PERF_SET</a>
 

 

