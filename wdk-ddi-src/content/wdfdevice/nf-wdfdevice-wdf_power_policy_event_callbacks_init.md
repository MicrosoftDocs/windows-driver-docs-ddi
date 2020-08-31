---
UID: NF:wdfdevice.WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
title: WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function (wdfdevice.h)
description: The WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function initializes a driver's WDF_POWER_POLICY_EVENT_CALLBACKS structure.
old-location: wdf\wdf_power_policy_event_callbacks_init.htm
tech.root: wdf
ms.assetid: 09ab4995-58be-4d87-adf7-e843e637ac09
ms.date: 02/26/2018
keywords: ["WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function"]
ms.keywords: DFDeviceObjectGeneralRef_46bebe7b-91e3-4ad3-b535-233d6c40622e.xml, WDF_POWER_POLICY_EVENT_CALLBACKS_INIT, WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function, kmdf.wdf_power_policy_event_callbacks_init, wdf.wdf_power_policy_event_callbacks_init, wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
 - wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_POWER_POLICY_EVENT_CALLBACKS_INIT
---

# WDF_POWER_POLICY_EVENT_CALLBACKS_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_policy_event_callbacks">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure.

## -parameters

### -param Callbacks 

[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_policy_event_callbacks">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure.

## -remarks

The <b>WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_policy_event_callbacks">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure and sets the structures <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

<div class="code"></div>

