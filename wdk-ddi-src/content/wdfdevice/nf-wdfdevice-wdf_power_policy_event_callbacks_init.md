---
UID: NF:wdfdevice.WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
title: WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: The WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function initializes a driver's WDF_POWER_POLICY_EVENT_CALLBACKS structure.
old-location: wdf\wdf_power_policy_event_callbacks_init.htm
old-project: wdf
ms.assetid: 09ab4995-58be-4d87-adf7-e843e637ac09
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , A, B, C, D, DFDeviceObjectGeneralRef_46bebe7b-91e3-4ad3-b535-233d6c40622e.xml, E, F, I, K, L, N, O, P, R, S, T, V, W, WDF_POWER_POLICY_EVENT_CALLBACKS_INIT, WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function, Y, _, kmdf.wdf_power_policy_event_callbacks_init, wdf.wdf_power_policy_event_callbacks_init, wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS_INIT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</b> function initializes a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_policy_event_callbacks.md">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure.


## -syntax


````
VOID WDF_POWER_POLICY_EVENT_CALLBACKS_INIT(
  _Out_ PWDF_POWER_POLICY_EVENT_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [out]

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_policy_event_callbacks.md">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



The <b>WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_policy_event_callbacks.md">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure and sets the structures <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

<div class="code"></div>


