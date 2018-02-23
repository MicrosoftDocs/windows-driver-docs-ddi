---
UID: NE:wdfio._WDF_IO_FORWARD_PROGRESS_ACTION
title: "_WDF_IO_FORWARD_PROGRESS_ACTION"
author: windows-driver-content
description: The WDF_IO_FORWARD_PROGRESS_ACTION enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation.
old-location: wdf\wdf_io_forward_progress_action.htm
old-project: wdf
ms.assetid: 4d63c908-8ae3-4df4-826f-9d87ea6c24ad
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdfio/WDF_IO_FORWARD_PROGRESS_ACTION, wdfio/WdfIoForwardProgressActionInvalid, DFQueueObjectRef_d1ee566a-9887-44de-aef5-a13f64e7603c.xml, wdfio/WdfIoForwardProgressActionFailRequest, WDF_IO_FORWARD_PROGRESS_ACTION, WdfIoForwardProgressActionFailRequest, kmdf.wdf_io_forward_progress_action, wdfio/WdfIoForwardProgressActionUseReservedRequest, WdfIoForwardProgressActionUseReservedRequest, WDF_IO_FORWARD_PROGRESS_ACTION enumeration, _WDF_IO_FORWARD_PROGRESS_ACTION, wdf.wdf_io_forward_progress_action, WdfIoForwardProgressActionInvalid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfio.h
apiname:
-	WDF_IO_FORWARD_PROGRESS_ACTION
product: Windows
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_ACTION
req.product: Windows 10 or later.
---

# _WDF_IO_FORWARD_PROGRESS_ACTION enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_FORWARD_PROGRESS_ACTION</b> enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation.


## -syntax


````
typedef enum _WDF_IO_FORWARD_PROGRESS_ACTION { 
  WdfIoForwardProgressActionInvalid             = 0x0,
  WdfIoForwardProgressActionFailRequest         = 0x1,
  WdfIoForwardProgressActionUseReservedRequest  = 0x2
} WDF_IO_FORWARD_PROGRESS_ACTION;
````


## -enum-fields




### -field WdfIoForwardProgressActionInvalid

For internal use only.


### -field WdfIoForwardProgressActionFailRequest

The framework will complete the current I/O request with an error status value.


### -field WdfIoForwardProgressActionUseReservedRequest

The framework will use a reserved request object, if one is available, for the current I/O request.


## -remarks



The <b>WDF_IO_FORWARD_PROGRESS_ACTION</b> enumeration is used as the return value for the <a href="..\wdfio\nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress.md">EvtIoWdmIrpForForwardProgress</a> callback function.




## -see-also

<a href="..\wdfio\nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress.md">EvtIoWdmIrpForForwardProgress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_FORWARD_PROGRESS_ACTION enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

