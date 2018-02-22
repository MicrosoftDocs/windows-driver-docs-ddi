---
UID: NE:wdfrequest._WDF_REQUEST_STOP_ACTION_FLAGS
title: "_WDF_REQUEST_STOP_ACTION_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_STOP_ACTION_FLAGS enumeration type defines flags that the framework passes to a driver's EvtIoStop callback function.
old-location: wdf\wdf_request_stop_action_flags.htm
old-project: wdf
ms.assetid: 01f95aee-60aa-4d6f-88a9-c0fa6ea6a09a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfRequestStopRequestCancelable, wdf.wdf_request_stop_action_flags, wdfrequest/WdfRequestStopActionSuspend, DFRequestObjectRef_e291c6a5-1e65-4505-9090-19e6ea66e7b3.xml, kmdf.wdf_request_stop_action_flags, WDF_REQUEST_STOP_ACTION_FLAGS, _WDF_REQUEST_STOP_ACTION_FLAGS, wdfrequest/WdfRequestStopActionPurge, wdfrequest/WDF_REQUEST_STOP_ACTION_FLAGS, WdfRequestStopActionInvalid, wdfrequest/WdfRequestStopActionInvalid, WdfRequestStopActionSuspend, wdfrequest/WdfRequestStopRequestCancelable, WDF_REQUEST_STOP_ACTION_FLAGS enumeration, WdfRequestStopActionPurge
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_STOP_ACTION_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_STOP_ACTION_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_STOP_ACTION_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_STOP_ACTION_FLAGS</b> enumeration type defines flags that the framework passes to a driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function.


## -syntax


````
typedef enum _WDF_REQUEST_STOP_ACTION_FLAGS { 
  WdfRequestStopActionInvalid      = 0,
  WdfRequestStopActionSuspend      = 0x01,
  WdfRequestStopActionPurge        = 0x2,
  WdfRequestStopRequestCancelable  = 0x10000000
} WDF_REQUEST_STOP_ACTION_FLAGS;
````


## -enum-fields




### -field WdfRequestStopActionInvalid

Reserved for internal use only.


### -field WdfRequestStopActionSuspend

The framework is stopping the I/O queue because the device is leaving its working (D0) state.


### -field WdfRequestStopActionPurge

The framework is stopping the I/O queue because the device is being removed. 


### -field WdfRequestStopRequestCancelable

The I/O request is cancelable.


## -remarks



When the framework calls a driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function, it sets either the <b>WdfRequestStopActionSuspend</b> or <b>WdfRequestStopActionPurge</b> flag. If the request is cancelable, the framework also sets the <b>WdfRequestStopRequestCancelable</b> flag.




## -see-also

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_STOP_ACTION_FLAGS enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

