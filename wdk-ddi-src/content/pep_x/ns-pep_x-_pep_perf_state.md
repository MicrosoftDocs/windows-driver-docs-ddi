---
UID: NS:pep_x._PEP_PERF_STATE
title: "_PEP_PERF_STATE"
author: windows-driver-content
description: The PEP_PERF_STATE structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values.
old-location: kernel\pep_perf_state.htm
old-project: kernel
ms.assetid: D5C9EF42-B6FE-4472-8188-2B23F87FA475
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.pep_perf_state, PEP_PERF_STATE, _PEP_PERF_STATE, pepfx/PEP_PERF_STATE, PEP_PERF_STATE structure [Kernel-Mode Driver Architecture], PPEP_PERF_STATE, pepfx/PPEP_PERF_STATE, PPEP_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], *PPEP_PERF_STATE
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
-	PEP_PERF_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PERF_STATE, *PPEP_PERF_STATE, PEP_PERF_STATE, *PPEP_PERF_STATE
---

# _PEP_PERF_STATE structure


## -description


The <b>PEP_PERF_STATE</b> structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values.


## -syntax


````
typedef struct _PEP_PERF_STATE {
  ULONGLONG Value;
  PVOID     Context;
} PEP_PERF_STATE, *PPEP_PERF_STATE;
````


## -struct-fields




### -field Value

The discrete value represented by this P-state. For more information, see Remarks.


### -field Context

A pointer to PEP-defined context data. The PEP uses this context to contain additional information about the discrete performance level that cannot be expressed in the <b>Value</b> member. This context is opaque to the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The <b>Context</b> member is optional and can be set to NULL.


## -remarks



The <b>Discrete.States</b> member of the <a href="..\pep_x\ns-pep_x-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a> structure is a pointer to an array of <b>PEP_PERF_STATE</b> structures. The <b>Unit</b> member of the <b>PEP_COMPONENT_PERF_SET</b> structure specifies the units in which the <b>Value</b> member in each array element is expressed. Component performance can be expressed in hertz (frequency) or in bits per second (bandwidth). For example, if <b>Value</b> = 100,000,000 and <b>Unit</b> = <b>PepPerfStateUnitFrequency</b>, this performance state represents a frequency of 100 megahertz.

Device drivers use the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_perf_state.md">PO_FX_PERF_STATE</a> structure, which is similar to the <b>PEP_PERF_STATE</b> structure.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_po_fx_perf_state.md">PO_FX_PERF_STATE</a>



<a href="..\pep_x\ns-pep_x-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PERF_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

