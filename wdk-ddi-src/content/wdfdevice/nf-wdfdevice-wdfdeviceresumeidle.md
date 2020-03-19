---
UID: NF:wdfdevice.WdfDeviceResumeIdle
title: WdfDeviceResumeIdle macro (wdfdevice.h)
description: The WdfDeviceResumeIdle method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.
old-location: wdf\wdfdeviceresumeidle.htm
tech.root: wdf
ms.assetid: d63848e8-0e6a-4ad7-a147-8804869b9c9b
ms.date: 02/26/2018
keywords: ["WdfDeviceResumeIdle macro"]
ms.keywords: DFDeviceObjectGeneralRef_6078e8e8-7d4e-4714-a1b4-74fc973a678c.xml, WdfDeviceResumeIdle, WdfDeviceResumeIdle method, kmdf.wdfdeviceresumeidle, wdf.wdfdeviceresumeidle, wdfdevice/WdfDeviceResumeIdle
f1_keywords:
 - "wdfdevice/WdfDeviceResumeIdle"
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
req.irql: <= DISPATCH_LEVEL
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
- WdfDeviceResumeIdle
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceResumeIdle macro


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceResumeIdle</b> method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.


Every call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> must eventually be followed by a call to <b>WdfDeviceResumeIdle</b>, or else the device will never return to a low-power state if it again becomes idle.

Calling <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdeviceresumeidlewithtag">WdfDeviceResumeIdleWithTag</a> instead of <b>WdfDeviceResumeIdle</b> provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers.


#### Examples

The following code example informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.

```cpp
WdfDeviceResumeIdle(device);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/debugging-power-reference-leaks-in-wdf">Debugging Power Reference Leaks in WDF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdeviceresumeidlewithtag">WdfDeviceResumeIdleWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevicestopidlewithtag">WdfDeviceStopIdleWithTag</a>
 

 

