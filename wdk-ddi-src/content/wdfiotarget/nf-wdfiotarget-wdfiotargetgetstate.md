---
UID: NF:wdfiotarget.WdfIoTargetGetState
title: WdfIoTargetGetState function (wdfiotarget.h)
description: The WdfIoTargetGetState method returns state information for a local or remote I/O target.
old-location: wdf\wdfiotargetgetstate.htm
tech.root: wdf
ms.assetid: 38e22922-d9de-4dfd-9da9-c131b789f5d6
ms.date: 02/26/2018
keywords: ["WdfIoTargetGetState function"]
ms.keywords: DFIOTargetRef_a11b8879-0766-4071-b1bd-c4cd43a0973b.xml, WdfIoTargetGetState, WdfIoTargetGetState method, kmdf.wdfiotargetgetstate, wdf.wdfiotargetgetstate, wdfiotarget/WdfIoTargetGetState
req.header: wdfiotarget.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoTargetGetState
 - wdfiotarget/WdfIoTargetGetState
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
 - WdfIoTargetGetState
---

# WdfIoTargetGetState function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetGetState</b> method returns state information for a local or remote I/O target.

## -parameters

### -param IoTarget 

[in]
A handle to a local or remote I/O target object that was obtained from a previous call to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.

## -returns

<b>WdfIoTargetGetState</b> returns a <a href="/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_state">WDF_IO_TARGET_STATE</a>-typed value that indicates the state of the specified I/O target.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about <b>WdfIoTargetGetState</b>, see <a href="/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example obtains state information for a USB I/O target.

```cpp
WDF_IO_TARGET_STATE  ioTargetState;

ioTargetState = WdfIoTargetGetState(WdfUsbTargetPipeGetIoTarget(pipeHandle));
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_state">WDF_IO_TARGET_STATE</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>