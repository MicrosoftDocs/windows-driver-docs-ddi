---
UID: NF:wdfdevice.WDF_PNPPOWER_EVENT_CALLBACKS_INIT
title: WDF_PNPPOWER_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: The WDF_PNPPOWER_EVENT_CALLBACKS_INIT function initializes a driver's WDF_PNPPOWER_EVENT_CALLBACKS structure.
old-location: wdf\wdf_pnppower_event_callbacks_init.htm
old-project: wdf
ms.assetid: f84e200b-542d-4885-a091-9e311b4ab697
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WDF_PNPPOWER_EVENT_CALLBACKS_INIT, kmdf.wdf_pnppower_event_callbacks_init, WDF_PNPPOWER_EVENT_CALLBACKS_INIT, WDF_PNPPOWER_EVENT_CALLBACKS_INIT function, DFDeviceObjectGeneralRef_f8e5ea12-489b-4217-b05f-43a31ef891d0.xml, wdf.wdf_pnppower_event_callbacks_init
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
-	WDF_PNPPOWER_EVENT_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_PNPPOWER_EVENT_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_PNPPOWER_EVENT_CALLBACKS_INIT</b> function initializes a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_pnppower_event_callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -syntax


````
VOID WDF_PNPPOWER_EVENT_CALLBACKS_INIT(
  _Out_ PWDF_PNPPOWER_EVENT_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [out]

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_pnppower_event_callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



The <b>WDF_PNPPOWER_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_pnppower_event_callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_PNPPOWER_EVENT_CALLBACKS_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>.

<div class="code"></div>


