---
UID: NF:wdfdevice.WdfDeviceWdmDispatchPreprocessedIrp
title: WdfDeviceWdmDispatchPreprocessedIrp function (wdfdevice.h)
description: The WdfDeviceWdmDispatchPreprocessedIrp method returns a preprocessed IRP to the framework.
old-location: wdf\wdfdevicewdmdispatchpreprocessedirp.htm
tech.root: wdf
ms.assetid: 83b18680-0b58-4278-87ff-757eb6e76178
ms.date: 02/26/2018
keywords: ["WdfDeviceWdmDispatchPreprocessedIrp function"]
ms.keywords: DFDeviceObjectGeneralRef_e861729e-006d-413c-9f7e-60e2fae72c1f.xml, WdfDeviceWdmDispatchPreprocessedIrp, WdfDeviceWdmDispatchPreprocessedIrp method, kmdf.wdfdevicewdmdispatchpreprocessedirp, wdf.wdfdevicewdmdispatchpreprocessedirp, wdfdevice/WdfDeviceWdmDispatchPreprocessedIrp
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
 - WdfDeviceWdmDispatchPreprocessedIrp
 - wdfdevice/WdfDeviceWdmDispatchPreprocessedIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceWdmDispatchPreprocessedIrp
---

# WdfDeviceWdmDispatchPreprocessedIrp function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceWdmDispatchPreprocessedIrp</b> method returns a  preprocessed IRP to the framework.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Irp 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure.

## -returns

<b>WdfDeviceWdmDispatchPreprocessedIrp</b> returns an NTSTATUS value that the framework or the driver provides as the result of processing the IRP. The driver must use this return value as the return value for the <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

A framework-based driver that preprocesses or postprocesses WDM IRPs must call <b>WdfDeviceWdmDispatchPreprocessedIrp</b>, typically from within the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function. For more information about how to call <b>WdfDeviceWdmDispatchPreprocessedIrp</b>, see <a href="/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">Preprocessing and Postprocessing IRPs</a>.


#### Examples

For a code example that uses <b>WdfDeviceWdmDispatchPreprocessedIrp</b>, see <a href="/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">Preprocessing and Postprocessing IRPs</a>.

<div class="code"></div>