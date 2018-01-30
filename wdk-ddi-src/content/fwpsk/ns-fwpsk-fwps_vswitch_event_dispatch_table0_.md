---
UID: NS:fwpsk.FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_
title: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_
author: windows-driver-content
description: The FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure specifies a callout driver-supplied virtual switch event dispatch table.Note  FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 is a specific version of FWPS_VSWITCH_EVENT_DISPATCH_TABLE.
old-location: netvista\fwps_vswitch_event_dispatch_table0.htm
old-project: netvista
ms.assetid: 7e949e6d-7448-4f76-b8a1-6d050261fb21
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure [Network Drivers Starting with Windows Vista], FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, netvista.fwps_vswitch_event_dispatch_table0, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0, fwpsk/FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
---

# FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ structure


## -description


The <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</b> structure specifies a callout driver-supplied virtual switch event dispatch table.<div class="alert"><b>Note</b>  <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</b> is a specific version of <b>FWPS_VSWITCH_EVENT_DISPATCH_TABLE</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -syntax


````
typedef struct FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_ {
  _Maybenull_ FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0              vSwitchLifetimeNotifyFn;
  _Maybenull_ FWPS_VSWITCH_PORT_EVENT_CALLBACK0                  vSwitchPortEventNotifyFn;
  _Maybenull_ FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0             vSwitchInterfaceEventNotifyFn;
     _Maybenull_
   FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0 vSwitchFilterEngineReorderNotifyRn;
  _Maybenull_
   FWPS_VSWITCH_POLICY_EVENT_CALLBACK0             vSwitchPolicyEventNotifyFn;
  _Maybenull_
   FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0       vSwitchRuntimeStateSaveNotifyFn;
  _Maybenull_
   FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0    vSwitchRuntimeStateRestoreNotifyFn;
} FWPS_VSWITCH_EVENT_DISPATCH_TABLE0;
````


## -struct-fields




### -field vSwitchLifetimeNotifyFn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_lifetime_event_callback0.md">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchPortEventNotifyFn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_port_event_callback0.md">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchInterfaceEventNotifyFn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_interface_event_callback0.md">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchFilterEngineReorderNotifyRn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_filter_engine_reorder_callback0.md">FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</a> callback function or NULL.


### -field vSwitchPolicyEventNotifyFn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_policy_event_callback0.md">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a> callback function or NULL.


### -field vSwitchRuntimeStateSaveNotifyFn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_save_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a> callback function or NULL.


### -field vSwitchRuntimeStateRestoreNotifyFn

The entry point for the <a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a> callback function or NULL.


## -remarks


The callback driver passes a pointer to an initialized  FWPS_VSWITCH_EVENT_DISPATCH_TABLE0  structure to the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a> function.

The following definition is in fwpvi.h: 


#define FWPS_VSWITCH_EVENT_DISPATCH_TABLE FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 



## -see-also

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_lifetime_event_callback0.md">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_interface_event_callback0.md">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_save_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_port_event_callback0.md">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_policy_event_callback0.md">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0.md">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_vswitch_filter_engine_reorder_callback0.md">FWPS_VSWITCH_FILTER_ENGINE_REORDER_CALLBACK0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_EVENT_DISPATCH_TABLE0 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

