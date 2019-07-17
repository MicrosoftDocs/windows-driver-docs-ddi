---
UID: NF:wdfdevice.WDF_PNPPOWER_EVENT_CALLBACKS_INIT
title: WDF_PNPPOWER_EVENT_CALLBACKS_INIT function (wdfdevice.h)
description: The WDF_PNPPOWER_EVENT_CALLBACKS_INIT function initializes a driver's WDF_PNPPOWER_EVENT_CALLBACKS structure.
old-location: wdf\wdf_pnppower_event_callbacks_init.htm
tech.root: wdf
ms.assetid: f84e200b-542d-4885-a091-9e311b4ab697
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_f8e5ea12-489b-4217-b05f-43a31ef891d0.xml, WDF_PNPPOWER_EVENT_CALLBACKS_INIT, WDF_PNPPOWER_EVENT_CALLBACKS_INIT function, kmdf.wdf_pnppower_event_callbacks_init, wdf.wdf_pnppower_event_callbacks_init, wdfdevice/WDF_PNPPOWER_EVENT_CALLBACKS_INIT
ms.topic: function
f1_keywords:
 - "wdfdevice/WDF_PNPPOWER_EVENT_CALLBACKS_INIT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_PNPPOWER_EVENT_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_PNPPOWER_EVENT_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_PNPPOWER_EVENT_CALLBACKS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_pnppower_event_callbacks">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -parameters




### -param Callbacks [out]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_pnppower_event_callbacks">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



The <b>WDF_PNPPOWER_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_pnppower_event_callbacks">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_PNPPOWER_EVENT_CALLBACKS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>.

<div class="code"></div>


