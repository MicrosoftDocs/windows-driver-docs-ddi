---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_QUERY_REMOVE
title: EVT_WDF_IO_TARGET_QUERY_REMOVE (wdfiotarget.h)
description: A driver's EvtIoTargetQueryRemove event callback function indicates whether the framework can safely remove a specified remote I/O target's device.
old-location: wdf\evtiotargetqueryremove.htm
tech.root: wdf
ms.assetid: cb7c97e5-081e-44fc-a759-9a1ae81de41c
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_TARGET_QUERY_REMOVE callback function"]
ms.keywords: DFIOTargetRef_9a471005-a4c8-4918-bc4c-4147bd6018f0.xml, EVT_WDF_IO_TARGET_QUERY_REMOVE, EVT_WDF_IO_TARGET_QUERY_REMOVE callback, EvtIoTargetQueryRemove, EvtIoTargetQueryRemove callback function, kmdf.evtiotargetqueryremove, wdf.evtiotargetqueryremove, wdfiotarget/EvtIoTargetQueryRemove
f1_keywords:
 - "wdfiotarget/EvtIoTargetQueryRemove"
req.header: wdfiotarget.h
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
- WdfIoTarget.h
api_name:
- EvtIoTargetQueryRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_TARGET_QUERY_REMOVE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoTargetQueryRemove</i> event callback function indicates whether the framework can safely remove a specified remote I/O target's device. 


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -returns



The<i>EvtIoTargetQueryRemove</i> callback function must return STATUS_SUCCESS if the driver determines that the framework can safely remove the specified I/O target's device. Otherwise, this callback function must return STATUS_UNSUCCESSFUL.




## -remarks



If a driver's <i>EvtIoTargetQueryRemove</i> callback function returns STATUS_SUCCESS, the system allows the I/O target's device to be removed, unless another driver returns STATUS_UNSUCCESSFUL.

To register an <i>EvtIoTargetQueryRemove</i> callback function, place the callback function's address in the I/O target's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure. The <i>EvtIoTargetQueryRemove</i> callback function is optional. Not supplying this callback function is equivalent to returning STATUS_SUCCESS.

The <i>EvtIoTargetQueryRemove</i> callback function must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>, if the driver determines that the PnP manager can safely remove the target device.

The callback function must disable the driver's ability to send additional I/O requests to the I/O target.

For more information about the <i>EvtIoTargetQueryRemove</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_complete">EvtIoTargetRemoveComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>
 

 

