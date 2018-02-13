---
UID: NC:usbcamdi.PFNUSBCAMD_WaitOnDeviceEvent
title: PFNUSBCAMD_WaitOnDeviceEvent
author: windows-driver-content
description: The USBCAMD_WaitOnDeviceEvent service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications.
old-location: stream\usbcamd_waitondeviceevent.htm
old-project: stream
ms.assetid: b9767479-3ad9-4b47-82d1-70b54329e7b8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.usbcamd_waitondeviceevent, USBCAMD_WaitOnDeviceEvent routine [Streaming Media Devices], USBCAMD_WaitOnDeviceEvent, PFNUSBCAMD_WaitOnDeviceEvent, PFNUSBCAMD_WaitOnDeviceEvent, usbcamdi/USBCAMD_WaitOnDeviceEvent, usbcmdpr_854c2d35-c023-4d7a-8c2e-3e56d3150e41.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	USBCAMD_WaitOnDeviceEvent
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PFNUSBCAMD_WaitOnDeviceEvent callback


## -description


The <b>USBCAMD_WaitOnDeviceEvent</b> service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications.


## -prototype


````
PFNUSBCAMD_WaitOnDeviceEvent USBCAMD_WaitOnDeviceEvent;

NTSTATUS APIENTRY USBCAMD_WaitOnDeviceEvent(
  _In_ PVOID                      DeviceContext,
  _In_ ULONG                      PipeIndex,
  _In_ PVOID                      Buffer,
  _In_ ULONG                      BufferLength,
  _In_ PCOMMAND_COMPLETE_FUNCTION EventComplete,
  _In_ PVOID                      EventContext,
  _In_ BOOLEAN                    LoopBack
)
{ ... }
````


## -parameters




### -param DeviceContext [in]

A pointer to device-specific context.


### -param PipeIndex [in]

Specifies the index of the interrupt pipe.


### -param Buffer [in]

A pointer to the read buffer.


### -param BufferLength [in]

Length of the read buffer, in bytes.


### -param EventComplete [in]

Pointer to a camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>, which is called when the interrupt read is completed This value can be <b>NULL</b>.


### -param EventContext [in]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>.


### -param LoopBack [in]

Specifies if USBCAMD is to resubmit another read request to the interrupt pipe every time an interrupt read is completed. Set to <b>TRUE</b>


## -returns



<b>USBCAMD_WaitOnDeviceEvent</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The device has been removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:

The value passed in the <i>PipeIndex</i> argument is invalid.

The type of the pipe specified by the <i>PipeIndex</i> argument represents an invalid type of pipe.

A bulk read/write request already exists.

The <i>Buffer</i> argument is <b>NULL</b>.

The length specified in the BufferLength argument is smaller than the maximum packet size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The event work item is deferred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate a work item to read from the pipe.

</td>
</tr>
</table>
 




## -remarks



The typical usage scenario for this function is a camera with a snapshot button and an interrupt pipe associated with the button. When a user presses the snapshot button, the read request on the interrupt pipe is satisfied and the camera minidriver is called back. If the camera minidriver sets USBCAMD_CamControlFlag_EnableDeviceEvents in the <i>CamControlFlag</i> argument during the <a href="..\usbcamdi\nf-usbcamdi-usbcamd_initializenewinterface.md">USBCAMD_InitializeNewInterface</a> call, the STI monitor also is notified of the snapshot event.

<b>USBCAMD_WaitOnDeviceEvent</b> is not available in USBCAMD version 1.0.




## -see-also

<a href="..\usbcamdi\nf-usbcamdi-usbcamd_initializenewinterface.md">USBCAMD_InitializeNewInterface</a>



<a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>



<a href="..\usbcamdi\ns-usbcamdi-usbcamd_interface.md">USBCAMD_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_WaitOnDeviceEvent routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

