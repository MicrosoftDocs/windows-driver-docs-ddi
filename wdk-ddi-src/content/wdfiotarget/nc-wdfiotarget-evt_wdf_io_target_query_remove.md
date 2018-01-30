---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_QUERY_REMOVE
title: EVT_WDF_IO_TARGET_QUERY_REMOVE
author: windows-driver-content
description: A driver's EvtIoTargetQueryRemove event callback function indicates whether the framework can safely remove a specified remote I/O target's device.
old-location: wdf\evtiotargetqueryremove.htm
old-project: wdf
ms.assetid: cb7c97e5-081e-44fc-a759-9a1ae81de41c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtiotargetqueryremove, EvtIoTargetQueryRemove callback function, EvtIoTargetQueryRemove, EVT_WDF_IO_TARGET_QUERY_REMOVE, EVT_WDF_IO_TARGET_QUERY_REMOVE, wdfiotarget/EvtIoTargetQueryRemove, DFIOTargetRef_9a471005-a4c8-4918-bc4c-4147bd6018f0.xml, kmdf.evtiotargetqueryremove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfIoTarget.h
apiname:
-	EvtIoTargetQueryRemove
product: Windows
targetos: Windows
req.typenames: "*PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY"
req.product: Windows 10 or later.
---

# EVT_WDF_IO_TARGET_QUERY_REMOVE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoTargetQueryRemove</i> event callback function indicates whether the framework can safely remove a specified remote I/O target's device. 


## -prototype


````
EVT_WDF_IO_TARGET_QUERY_REMOVE EvtIoTargetQueryRemove;

NTSTATUS EvtIoTargetQueryRemove(
  _In_ WDFIOTARGET IoTarget
)
{ ... }
````


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -returns


The<i>EvtIoTargetQueryRemove</i> callback function must return STATUS_SUCCESS if the driver determines that the framework can safely remove the specified I/O target's device. Otherwise, this callback function must return STATUS_UNSUCCESSFUL.



## -remarks


If a driver's <i>EvtIoTargetQueryRemove</i> callback function returns STATUS_SUCCESS, the system allows the I/O target's device to be removed, unless another driver returns STATUS_UNSUCCESSFUL.

To register an <i>EvtIoTargetQueryRemove</i> callback function, place the callback function's address in the I/O target's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. The <i>EvtIoTargetQueryRemove</i> callback function is optional. Not supplying this callback function is equivalent to returning STATUS_SUCCESS.

The <i>EvtIoTargetQueryRemove</i> callback function must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>, if the driver determines that the PnP manager can safely remove the target device.

The callback function must disable the driver's ability to send additional I/O requests to the I/O target.

For more information about the <i>EvtIoTargetQueryRemove</i> callback function, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.



## -see-also

<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a>

<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_complete.md">EvtIoTargetRemoveComplete</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>

<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_TARGET_QUERY_REMOVE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

