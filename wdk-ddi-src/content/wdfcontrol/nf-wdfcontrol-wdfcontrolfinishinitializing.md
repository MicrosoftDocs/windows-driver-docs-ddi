---
UID: NF:wdfcontrol.WdfControlFinishInitializing
title: WdfControlFinishInitializing function (wdfcontrol.h)
description: The WdfControlFinishInitializing method informs the framework that a driver has finished initializing a specified control device object.
old-location: wdf\wdfcontrolfinishinitializing.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfControlFinishInitializing function"]
ms.keywords: DFDeviceObjectControllerDevObjRef_af1b91cc-0f6c-4b03-b168-5ac1357f2dc3.xml, WdfControlFinishInitializing, WdfControlFinishInitializing method, kmdf.wdfcontrolfinishinitializing, wdf.wdfcontrolfinishinitializing, wdfcontrol/WdfControlFinishInitializing
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: CtlDeviceFinishInitDeviceAdd, CtlDeviceFinishInitDrEntry, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfControlFinishInitializing
 - wdfcontrol/WdfControlFinishInitializing
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfControlFinishInitializing
---

# WdfControlFinishInitializing function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfControlFinishInitializing</b> method informs the framework that a driver has finished initializing a specified control device object.

## -parameters

### -param Device [in]


A handle to a control device object.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The system will not send I/O requests or Windows Management Instrumentation (WMI) requests to a control device object unless the driver has called <b>WdfControlFinishInitializing</b>.

For more information about control device objects and calling <b>WdfControlFinishInitializing</b>, see <a href="/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.


#### Examples

For a code example that uses <b>WdfControlFinishInitializing</b>, see <a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>.

<div class="code"></div>
