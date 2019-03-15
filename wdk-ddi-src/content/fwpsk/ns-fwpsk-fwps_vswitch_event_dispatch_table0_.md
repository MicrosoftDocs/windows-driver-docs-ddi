---
UID: NS:fwpsk.FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_
title: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ (fwpsk.h)
description: The FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure specifies a callout driver-supplied virtual switch event dispatch table.Note  FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 is a specific version of FWPS_VSWITCH_EVENT_DISPATCH_TABLE.
old-location: netvista\fwps_vswitch_event_dispatch_table0.htm
tech.root: netvista
ms.assetid: 7e949e6d-7448-4f76-b8a1-6d050261fb21
ms.date: 05/02/2018
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure [Network Drivers Starting with Windows Vista], FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, fwpsk/FWPS_VSWITCH_EVENT_DISPATCH_TABLE0, netvista.fwps_vswitch_event_dispatch_table0
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fwpsk.h
api_name:
- FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
product:
- Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
---

# FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ structure


## -description


The <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</b> structure specifies a callout driver-supplied virtual switch event dispatch table.<div class="alert"><b>Note</b>  <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</b> is a specific version of <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -struct-fields




### -field vSwitchLifetimeNotifyFn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451271">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchPortEventNotifyFn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451276">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchInterfaceEventNotifyFn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451269">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchFilterEngineReorderNotifyRn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451267">FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</a> callback function or NULL.


### -field vSwitchPolicyEventNotifyFn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451272">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchRuntimeStateSaveNotifyFn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451286">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a> callback function or NULL.


### -field vSwitchRuntimeStateRestoreNotifyFn

The entry point for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451281">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a> callback function or NULL.


## -remarks



The callback driver passes a pointer to an initialized  FWPS_VSWITCH_EVENT_DISPATCH_TABLE0  structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a> function.

The following definition is in fwpvi.h: 

`#define FWPS_VSWITCH_EVENT_DISPATCH_TABLE FWPS_VSWITCH_EVENT_DISPATCH_TABLE0`




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451267">FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451269">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451271">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451272">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451276">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451281">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451286">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 

 

