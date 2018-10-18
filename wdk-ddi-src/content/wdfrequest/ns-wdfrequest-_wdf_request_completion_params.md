---
UID: NS:wdfrequest._WDF_REQUEST_COMPLETION_PARAMS
title: "_WDF_REQUEST_COMPLETION_PARAMS"
author: windows-driver-content
description: The WDF_REQUEST_COMPLETION_PARAMS structure contains parameters that are associated with the completion of an I/O request.
old-location: wdf\wdf_request_completion_params.htm
tech.root: wdf
ms.assetid: e3993202-c49d-4de9-8881-9e3786575e17
ms.date: 2/26/2018
ms.keywords: "*PWDF_REQUEST_COMPLETION_PARAMS, DFRequestObjectRef_e8277b90-7e1e-4d00-9f6b-012b189c153f.xml, PWDF_REQUEST_COMPLETION_PARAMS, PWDF_REQUEST_COMPLETION_PARAMS structure pointer, WDF_REQUEST_COMPLETION_PARAMS, WDF_REQUEST_COMPLETION_PARAMS structure, _WDF_REQUEST_COMPLETION_PARAMS, kmdf.wdf_request_completion_params, wdf.wdf_request_completion_params, wdfrequest/PWDF_REQUEST_COMPLETION_PARAMS, wdfrequest/WDF_REQUEST_COMPLETION_PARAMS"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
-	WDF_REQUEST_COMPLETION_PARAMS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_COMPLETION_PARAMS, *PWDF_REQUEST_COMPLETION_PARAMS
---

# _WDF_REQUEST_COMPLETION_PARAMS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_COMPLETION_PARAMS</b> structure contains parameters that are associated with the completion of an I/O request.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Type

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a> value that identifies the request type.


### -field IoStatus

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure for the request.


### -field Parameters

Request-specific values for the request.


### -field Parameters.Write


### -field Parameters.Write.Buffer

A handle to a framework memory object. This object identifies the buffer that the driver specified when it formatted the request and sent it to an I/O target.


### -field Parameters.Write.Length

Length, in bytes, of the transfer.


### -field Parameters.Write.Offset

Beginning address within the buffer for the data transfer.


### -field Parameters.Read


### -field Parameters.Read.Buffer

A handle to a framework memory object. This object identifies the buffer that the driver specified when it formatted the request and sent it to an I/O target.


### -field Parameters.Read.Length

Length, in bytes, of the transfer.


### -field Parameters.Read.Offset

Beginning address within the buffer for the data transfer.


### -field Parameters.Ioctl


### -field Parameters.Ioctl.IoControlCode

 


### -field Parameters.Ioctl.Input


### -field Parameters.Ioctl.Input.Buffer

A handle to a framework memory object. This object identifies the input buffer that the driver specified when it formatted the request and sent it to an I/O target.


### -field Parameters.Ioctl.Input.Offset

Beginning address within the buffer for the data transfer.


### -field Parameters.Ioctl.Output


### -field Parameters.Ioctl.Output.Buffer

A handle to a framework memory object. This object identifies the output buffers that the driver specified when it formatted the request and sent it to an I/O target.


### -field Parameters.Ioctl.Output.Offset

Beginning address within the buffer for the data transfer.


### -field Parameters.Ioctl.Output.Length

Length, in bytes, of the transfer.


### -field Parameters.Others


### -field Parameters.Others.Argument1

Use of this member is defined by the driver stack.  See Remarks.


### -field Parameters.Others.Argument1.Ptr

 


### -field Parameters.Others.Argument1.Value

 


### -field Parameters.Others.Argument2

Use of this member is defined by the driver stack.


### -field Parameters.Others.Argument2.Ptr

 


### -field Parameters.Others.Argument2.Value

 


### -field Parameters.Others.Argument3

Use of this member is defined by the driver stack.


### -field Parameters.Others.Argument3.Ptr

 


### -field Parameters.Others.Argument3.Value

 


### -field Parameters.Others.Argument4

Use of this member is defined by the driver stack.


### -field Parameters.Others.Argument4.Ptr

 


### -field Parameters.Others.Argument4.Value

 


### -field Parameters.Usb

For USB devices, this member contains a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553049">WDF_USB_REQUEST_COMPLETION_PARAMS</a> structure.




### -field Parameters.Usb.Completion

 




## -remarks



The <b>WDF_REQUEST_COMPLETION_PARAMS</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549961">WdfRequestGetCompletionParams</a> method and a driver's <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function.

 In both cases, the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548612">WdfIoTargetFormatRequestForRead</a>.

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549961">WdfRequestGetCompletionParams</a> to retrieve the I/O completion information for a request, the driver must first call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552456">WDF_REQUEST_COMPLETION_PARAMS_INIT</a> to initialize the <b>WDF_REQUEST_COMPLETION_PARAMS</b> structure.

The <b>Parameters.Others.Argument</b>  members are custom arguments that a driver typically passes down the stack (and can arrive back after the request is completed).  They are used for non-standard, driver stack dependent data. For example, a USB driver specifies a pointer to a URB in  <b>Parameters.Others.Argument1</b> when it sends a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537271">IOCTL_INTERNAL_USB_SUBMIT_URB</a> request to the USB stack.  Similarly, a Bluetooth driver specifies a pointer to a  BRB (Bluetooth Request Block) in <b>Parameters.Others.Argument1</b> when it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536751">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>.




## -see-also




<a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552456">WDF_REQUEST_COMPLETION_PARAMS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549961">WdfRequestGetCompletionParams</a>
 

 

