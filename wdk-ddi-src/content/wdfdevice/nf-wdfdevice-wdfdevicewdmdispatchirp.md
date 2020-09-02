---
UID: NF:wdfdevice.WdfDeviceWdmDispatchIrp
title: WdfDeviceWdmDispatchIrp function (wdfdevice.h)
description: The WdfDeviceWdmDispatchIrp method returns a dispatched IRP to the framework from EvtDeviceWdmIrpDispatch.
old-location: wdf\wdfdevicewdmdispatchirp.htm
tech.root: wdf
ms.assetid: 362C6F7C-7B92-43A8-9BD0-F647FDD266E4
ms.date: 02/26/2018
keywords: ["WdfDeviceWdmDispatchIrp function"]
ms.keywords: WdfDeviceWdmDispatchIrp, WdfDeviceWdmDispatchIrp method, kmdf.wdfdevicewdmdispatchirp, wdf.wdfdevicewdmdispatchirp, wdfdevice/WdfDeviceWdmDispatchIrp
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.17
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceWdmDispatchIrp
 - wdfdevice/WdfDeviceWdmDispatchIrp
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
 - WdfDeviceWdmDispatchIrp
---

# WdfDeviceWdmDispatchIrp function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceWdmDispatchIrp</b> method returns a dispatched IRP to the framework from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a>.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Irp 

[in]
A pointer to an IRP structure.

### -param DispatchContext 

[in]
The dispatch context parameter the driver received in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a>  callback.

## -returns

The <b>WdfDeviceWdmDispatchIrp</b> method returns an NTSTATUS value that the framework or the driver provides as a result of processing the IRP. The driver must use this return value as the return value for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a> callback function that called <b>WdfDeviceWdmDispatchIrp</b>.

A bug check occurs if a KMDF  driver supplies an invalid object handle.  If a UMDF driver supplies an invalid handle, the driver host process terminates.

## -remarks

If your driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a> callback function, you can call <b>WdfDeviceWdmDispatchIrp</b> from within the callback function to return the IRP to the framework for default processing instead of dispatching it to a specific queue.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a>

