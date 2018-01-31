---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_REMOVE_COMPLETE
title: EVT_WDF_IO_TARGET_REMOVE_COMPLETE
author: windows-driver-content
description: A driver's EvtIoTargetRemoveComplete event callback function performs operations when the removal of a specified remote I/O target is complete.
old-location: wdf\evtiotargetremovecomplete.htm
old-project: wdf
ms.assetid: 204f101d-770c-4363-9371-0ee76dfa0b2c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtiotargetremovecomplete, EvtIoTargetRemoveComplete callback function, EvtIoTargetRemoveComplete, EVT_WDF_IO_TARGET_REMOVE_COMPLETE, EVT_WDF_IO_TARGET_REMOVE_COMPLETE, wdfiotarget/EvtIoTargetRemoveComplete, DFIOTargetRef_d0c566ce-1ed7-4adb-9988-bc1751f000e1.xml, kmdf.evtiotargetremovecomplete
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
-	EvtIoTargetRemoveComplete
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, *PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
req.product: Windows 10 or later.
---

# EVT_WDF_IO_TARGET_REMOVE_COMPLETE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoTargetRemoveComplete</i> event callback function performs operations when the removal of a specified remote I/O target is complete.


## -prototype


````
EVT_WDF_IO_TARGET_REMOVE_COMPLETE EvtIoTargetRemoveComplete;

VOID EvtIoTargetRemoveComplete(
  _In_ WDFIOTARGET IoTarget
)
{ ... }
````


## -parameters




#### - IoTarget [in]

A handle to an I/O target object. 


## -returns


None



## -remarks


To register an <i>EvtIoTargetRemoveComplete</i> callback function, place the callback function's address in the I/O target's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

The framework calls your driver's <i>EvtIoTargetRemoveComplete</i> callback function after the driver's <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function returns STATUS_SUCCESS, or after the device has been removed unexpectedly (surprise-removed).

A driver's <i>EvtIoTargetRemoveComplete</i> callback function must permanently close the remote I/O target by calling <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a>. Because the target device has been removed, the <i>EvtIoTargetRemoveComplete</i> callback function should also perform any additional target-removal operations that might be necessary, such as releasing system resources that the driver might have allocated when it opened the target.

The <i>EvtIoTargetRemoveComplete</i> callback function is optional. If the driver does not supply this callback function, the framework permanently closes the I/O target.

For more information about the <i>EvtIoTargetRemoveComplete</i> callback function, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.



## -see-also

<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a>

<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>

<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_TARGET_REMOVE_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

