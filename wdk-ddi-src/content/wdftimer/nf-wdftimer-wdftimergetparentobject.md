---
UID: NF:wdftimer.WdfTimerGetParentObject
title: WdfTimerGetParentObject function (wdftimer.h)
description: The WdfTimerGetParentObject method returns a handle to the parent object of a specified framework timer object.
old-location: wdf\wdftimergetparentobject.htm
tech.root: wdf
ms.assetid: 16ac6fea-9eea-4062-8ab9-fd14d80118a6
ms.date: 02/26/2018
keywords: ["WdfTimerGetParentObject function"]
ms.keywords: DFTimerObjectRef_b081e639-a1d6-4119-b47c-b95b772630bc.xml, WdfTimerGetParentObject, WdfTimerGetParentObject method, kmdf.wdftimergetparentobject, wdf.wdftimergetparentobject, wdftimer/WdfTimerGetParentObject
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfTimerGetParentObject
 - wdftimer/WdfTimerGetParentObject
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
 - WdfTimerGetParentObject
---

# WdfTimerGetParentObject function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfTimerGetParentObject</b> method returns a handle to the parent object of a specified framework timer object.

## -parameters

### -param Timer 

[in]
A handle to a framework timer object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a>.

## -returns

<b>WdfTimerGetParentObject</b> returns a handle to the framework object that is the specified timer object's parent object. 

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about framework timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.


#### Examples

The following code example shows now an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> callback function can obtain a timer object's parent. In this example, the driver previously specified that the timer object's parent is a queue object.

```cpp
VOID
MyEvtTimerFunc(
    IN WDFTIMER  Timer
    )
{
    WDFQUEUE queue;

    queue = WdfTimerGetParentObject(Timer);
...
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a>

