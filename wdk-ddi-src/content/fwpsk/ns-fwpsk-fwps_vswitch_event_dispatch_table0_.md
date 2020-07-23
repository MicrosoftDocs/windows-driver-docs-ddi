---
UID: NS:fwpsk.FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_
title: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ (fwpsk.h)
description: The FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure specifies a callout driver-supplied virtual switch event dispatch table.Note  FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 is a specific version of FWPS_VSWITCH_EVENT_DISPATCH_TABLE.
old-location: netvista\fwps_vswitch_event_dispatch_table0.htm
tech.root: netvista
ms.assetid: 7e949e6d-7448-4f76-b8a1-6d050261fb21
ms.date: 05/02/2018
keywords: ["FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ structure"]
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure [Network Drivers Starting with Windows Vista], FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, fwpsk/FWPS_VSWITCH_EVENT_DISPATCH_TABLE0, netvista.fwps_vswitch_event_dispatch_table0
f1_keywords:
 - "fwpsk/FWPS_VSWITCH_EVENT_DISPATCH_TABLE0"
 - "FWPS_VSWITCH_EVENT_DISPATCH_TABLE0"
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
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
---

# FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ structure


## -description


The <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</b> structure specifies a callout driver-supplied virtual switch event dispatch table.<div class="alert"><b>Note</b>  <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</b> is a specific version of <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -struct-fields




### -field vSwitchLifetimeNotifyFn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_lifetime_event_callback0">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchPortEventNotifyFn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_port_event_callback0">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchInterfaceEventNotifyFn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_interface_event_callback0">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchFilterEngineReorderNotifyRn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_filter_engine_reorder_callback0">FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</a> callback function or NULL.


### -field vSwitchPolicyEventNotifyFn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_policy_event_callback0">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchRuntimeStateSaveNotifyFn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_save_callback0">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a> callback function or NULL.


### -field vSwitchRuntimeStateRestoreNotifyFn

The entry point for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a> callback function or NULL.


## -remarks



The callback driver passes a pointer to an initialized  FWPS_VSWITCH_EVENT_DISPATCH_TABLE0  structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a> function.

The following definition is in fwpvi.h: 

`#define FWPS_VSWITCH_EVENT_DISPATCH_TABLE FWPS_VSWITCH_EVENT_DISPATCH_TABLE0`




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_filter_engine_reorder_callback0">FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_interface_event_callback0">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_lifetime_event_callback0">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_policy_event_callback0">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_port_event_callback0">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_save_callback0">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 

 

