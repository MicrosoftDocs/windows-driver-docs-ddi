---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_IRP_PREPROCESS
title: EVT_WDFDEVICE_WDM_IRP_PREPROCESS (wdfdevice.h)
description: A driver's EvtDeviceWdmIrpPreprocess event callback function receives an IRP before the framework processes the IRP.
old-location: wdf\evtdevicewdmirppreprocess.htm
tech.root: wdf
ms.assetid: aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a
ms.date: 02/26/2018
keywords: ["EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback function"]
ms.keywords: DFDeviceObjectGeneralRef_7329adf6-5814-40cb-ac9b-a7fb67b5f05c.xml, EVT_WDFDEVICE_WDM_IRP_PREPROCESS, EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback, EvtDeviceWdmIrpPreprocess, EvtDeviceWdmIrpPreprocess callback function, kmdf.evtdevicewdmirppreprocess, wdf.evtdevicewdmirppreprocess, wdfdevice/EvtDeviceWdmIrpPreprocess
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDFDEVICE_WDM_IRP_PREPROCESS
 - wdfdevice/EVT_WDFDEVICE_WDM_IRP_PREPROCESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceWdmIrpPreprocess
---

# EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceWdmIrpPreprocess</i> event callback function receives an IRP before the framework processes the IRP.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Irp 

[in, out]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure.

## -returns

The <i>EvtDeviceWdmIrpPreprocess</i> callback function must:


<ul>
<li>Set the <b>IoStatus.Status</b> member of the IRP to STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(status) equals <b>TRUE</b>, and return the same value (after calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>), if the callback function successfully completes the received IRP.</li>
<li>Set the <b>IoStatus.Status</b> member of the IRP to a status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(status) equals <b>FALSE</b>, and return the same value (after calling IoCompleteRequest), if the callback function detects an error. </li>
<li>Return STATUS_PENDING, if the callback function calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending">IoMarkIrpPending</a>. 
</li>
<li>Return the value that the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a> method returns, if the callback function calls that method. 
</li>
</ul>

## -remarks

To register an <i>EvtDeviceWdmIrpPreprocess</i> callback function, your driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback">WdfDeviceInitAssignWdmIrpPreprocessCallback</a>. 

Your driver can use an <i>EvtDeviceWdmIrpPreprocess</i> callback function to do any, or all, of the following:

<ul>
<li>
 Handle an IRP that the framework does not support, by following the <a href="/windows-hardware/drivers/kernel/handling-irps">WDM rules for handling IRPs</a>. 

</li>
<li>
 Preprocess an IRP before the framework handles it. 

</li>
<li>
 Set a completion routine so that the driver can postprocess an IRP after the framework handles it. 

</li>
</ul>
For more information about how to implement an <i>EvtDeviceWdmIrpPreprocess</i> callback function, see <a href="/windows-hardware/drivers/wdf/handling-wdm-irps-outside-of-the-framework">Handling WDM IRPs Outside of the Framework</a>.

If you want the framework to subsequently handle the IRP as it would if the <i>EvtDeviceWdmIrpPreprocess</i> callback function had not been called, the callback function must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a> to return the IRP to the framework.

If your driver registers an <i>EvtDeviceWdmIrpPreprocess</i> callback function, the framework adds an additional <a href="/windows-hardware/drivers/kernel/i-o-stack-locations">I/O stack location</a> to IRPs that the callback function receives. The additional I/O stack location allows the callback function to set an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine before it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a>.

The <i>EvtDeviceWdmIrpPreprocess</i> callback function is called at the IRQL of the calling thread. The IRQL is determined by the type of IRP that the framework is passing to <i>EvtDeviceWdmIrpPreprocess</i>. For example, if the PnP manager sends <a href="/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a> at IRQL = PASSIVE_LEVEL, the framework calls <i>EvtDeviceWdmIrpPreprocess</i> at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback">WdfDeviceInitAssignWdmIrpPreprocessCallback</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a>