---
UID: NF:wdfdevice.WdfDeviceWdmDispatchPreprocessedIrp
title: WdfDeviceWdmDispatchPreprocessedIrp function
author: windows-driver-content
description: The WdfDeviceWdmDispatchPreprocessedIrp method returns a preprocessed IRP to the framework.
old-location: wdf\wdfdevicewdmdispatchpreprocessedirp.htm
old-project: wdf
ms.assetid: 83b18680-0b58-4278-87ff-757eb6e76178
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceWdmDispatchPreprocessedIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceWdmDispatchPreprocessedIrp
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
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
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceWdmDispatchPreprocessedIrp function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceWdmDispatchPreprocessedIrp</b> method returns a  preprocessed IRP to the framework.



## -syntax

````
NTSTATUS WdfDeviceWdmDispatchPreprocessedIrp(
  _In_ WDFDEVICE Device,
  _In_ PIRP      Irp
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Irp [in]

A pointer to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure.


## -returns
<b>WdfDeviceWdmDispatchPreprocessedIrp</b> returns an NTSTATUS value that that framework or the driver provides as the result of processing the IRP. The driver must use this return value as the return value for the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
A framework-based driver that preprocesses or postprocesses WDM IRPs must call <b>WdfDeviceWdmDispatchPreprocessedIrp</b>, typically from within the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function. For more information about how to call <b>WdfDeviceWdmDispatchPreprocessedIrp</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">Preprocessing and Postprocessing IRPs</a>.

For a code example that uses <b>WdfDeviceWdmDispatchPreprocessedIrp</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/preprocessing-and-postprocessing-irps">Preprocessing and Postprocessing IRPs</a>.</p>