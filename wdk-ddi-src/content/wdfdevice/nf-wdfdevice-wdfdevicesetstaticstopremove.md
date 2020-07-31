---
UID: NF:wdfdevice.WdfDeviceSetStaticStopRemove
title: WdfDeviceSetStaticStopRemove function (wdfdevice.h)
description: The WdfDeviceSetStaticStopRemove method informs the framework whether a device can be stopped and removed.
old-location: wdf\wdfdevicesetstaticstopremove.htm
tech.root: wdf
ms.assetid: b2776618-2585-4a7a-9f8f-536f1d28745b
ms.date: 02/26/2018
keywords: ["WdfDeviceSetStaticStopRemove function"]
ms.keywords: DFDeviceObjectGeneralRef_9874b784-6344-4336-9753-0b172563f981.xml, WdfDeviceSetStaticStopRemove, WdfDeviceSetStaticStopRemove method, kmdf.wdfdevicesetstaticstopremove, wdf.wdfdevicesetstaticstopremove, wdfdevice/WdfDeviceSetStaticStopRemove
f1_keywords:
 - "wdfdevice/WdfDeviceSetStaticStopRemove"
 - "WdfDeviceSetStaticStopRemove"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceSetStaticStopRemove
targetos: Windows
req.typenames: 
---

# WdfDeviceSetStaticStopRemove function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceSetStaticStopRemove</b> method informs the framework whether a device can be stopped and removed.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Stoppable [in]

A Boolean value that indicates whether the specified device can be stopped and removed. If <b>TRUE</b>, the device can be stopped and removed. If <b>FALSE</b>, the device cannot be stopped and removed.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




By default, a device can be stopped and removed. Therefore, a driver typically calls <b>WdfDeviceSetStaticStopRemove</b> only if it must temporarily set the <i>Stoppable</i> parameter to <b>FALSE</b>. For example, a driver that controls a DVD writer might call <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>FALSE</b> before it begins burning a DVD. After the driver has finished burning the DVD, it would call <b>WdfDeviceSetStaticStopRemove</b> again with <i>Stoppable</i> set to <b>TRUE</b>.  

If your driver's device is supporting a special file (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetspecialfilesupport">WdfDeviceSetSpecialFileSupport</a>), the framework will not allow the device to be stopped or removed. In this case, your driver does not have to call <b>WdfDeviceSetStaticStopRemove</b> .

The driver must match every call to <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>FALSE</b> with a call to <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>TRUE</b>.

Calling <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>FALSE</b> does not prevent the framework from notifying the driver if the device is unexpectedly removed (surprise-removed).

For more information about how to prevent the operating system from stopping a device, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-requests-to-stop-a-device">Handling Requests to Stop a Device</a>.


#### Examples

The following code example informs the framework that the specified device cannot be stopped and removed.

```cpp
WdfDeviceSetStaticStopRemove(
                             device,
                             FALSE
                             );
```


