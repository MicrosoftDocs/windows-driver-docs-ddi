---
UID: NS:wdm._PO_FX_PERF_STATE
title: "_PO_FX_PERF_STATE"
description: The PO_FX_PERF_STATE structure represents a performance state for a single component within a device.
old-location: kernel\po_fx_perf_state.htm
tech.root: kernel
ms.assetid: 06A41593-A052-43A7-B3A7-02185B557FA3
ms.date: 04/30/2018
ms.keywords: "*PPO_FX_PERF_STATE, PO_FX_PERF_STATE, PO_FX_PERF_STATE structure [Kernel-Mode Driver Architecture], PPO_FX_PERF_STATE, PPO_FX_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], _PO_FX_PERF_STATE, kernel.po_fx_perf_state, wdm/PO_FX_PERF_STATE, wdm/PPO_FX_PERF_STATE"
ms.topic: struct
req.header: wdm.h
req.include-header: Wudfwdm.h
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
-	Wdm.h
api_name:
-	PO_FX_PERF_STATE
product:
- Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE, *PPO_FX_PERF_STATE
---

# _PO_FX_PERF_STATE structure


## -description


The <b>PO_FX_PERF_STATE</b> structure represents a performance state for a single component within a device.


## -struct-fields




### -field Value

The value of this performance state. The units are specified by the <b>Unit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> that contains this performance state. For example, if <b>Value</b> is 100000000 and the <b>Unit</b> member of the  <b>PO_FX_COMPONENT_PERF_SET</b> is <b>PoFxPerfStateUnitFrequency</b>, this performance state represents 100 MHz.


### -field Context

A pointer to additional context for the performance state that cannot be presented by the <b>Value</b> member. This data can be shared between the driver and the platform extension plug-in (PEP).

<div class="alert"><b>Note</b>  Using the <b>Context</b> member can hinder the visualization of performance states in Windows Performance Analyzer.</div>
<div> </div>

## -remarks



The <b>States</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> structure contains an array of <b>PO_FX_PERF_STATE</b> elements. 




## -see-also




<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939838">PO_FX_PERF_STATE_UNIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939778">PoFxRegisterComponentPerfStates</a>
 

 

