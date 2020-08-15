---
UID: NC:wdfdriver.EVT_WDF_DRIVER_UNLOAD
title: EVT_WDF_DRIVER_UNLOAD (wdfdriver.h)
description: A driver's EvtDriverUnload event callback function performs operations that must take place before the driver is unloaded.
old-location: wdf\evtdriverunload.htm
tech.root: wdf
ms.assetid: 2a2ed215-1b62-4ff1-bea6-e38fafbcf7d0
ms.date: 02/26/2018
keywords: ["EVT_WDF_DRIVER_UNLOAD callback function"]
ms.keywords: DFDriverObjectRef_4c29e844-1ad7-4d45-b01d-e03f841bb9dd.xml, EVT_WDF_DRIVER_UNLOAD, EVT_WDF_DRIVER_UNLOAD callback, EvtDriverUnload, EvtDriverUnload callback function, kmdf.evtdriverunload, wdf.evtdriverunload, wdfdriver/EvtDriverUnload
f1_keywords:
 - "wdfdriver/EvtDriverUnload"
 - "EvtDriverUnload"
req.header: wdfdriver.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdriver.h
api_name:
- EvtDriverUnload
targetos: Windows
req.typenames: 
---

# EVT_WDF_DRIVER_UNLOAD callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDriverUnload</i> event callback function performs operations that must take place before the driver is unloaded.


## -parameters




### -param Driver 
[in]
A handle to a framework driver object.


## -remarks

A driver registers an <i>EvtDriverUnload</i> callback function when it calls [**WdfDriverCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate).

The <i>EvtDriverUnload</i> callback function must deallocate any non-device-specific system resources that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine allocated.

The framework does not call a driver's 
    <i>EvtDriverUnload</i> callback function if the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine returns an error status value.

You must declare the function by using the EVT_WDF_DRIVER_UNLOAD type. For more information, see the following Example section.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>
 

 

