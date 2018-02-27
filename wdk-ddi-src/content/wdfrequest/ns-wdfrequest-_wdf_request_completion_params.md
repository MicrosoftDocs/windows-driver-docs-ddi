---
UID: NS:wdfrequest._WDF_REQUEST_COMPLETION_PARAMS
title: "_WDF_REQUEST_COMPLETION_PARAMS"
author: windows-driver-content
description: The WDF_REQUEST_COMPLETION_PARAMS structure contains parameters that are associated with the completion of an I/O request.
old-location: wdf\wdf_request_completion_params.htm
old-project: wdf
ms.assetid: e3993202-c49d-4de9-8881-9e3786575e17
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWDF_REQUEST_COMPLETION_PARAMS, DFRequestObjectRef_e8277b90-7e1e-4d00-9f6b-012b189c153f.xml, PWDF_REQUEST_COMPLETION_PARAMS, PWDF_REQUEST_COMPLETION_PARAMS structure pointer, WDF_REQUEST_COMPLETION_PARAMS, WDF_REQUEST_COMPLETION_PARAMS structure, _WDF_REQUEST_COMPLETION_PARAMS, kmdf.wdf_request_completion_params, wdf.wdf_request_completion_params, wdfrequest/PWDF_REQUEST_COMPLETION_PARAMS, wdfrequest/WDF_REQUEST_COMPLETION_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_COMPLETION_PARAMS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_COMPLETION_PARAMS, *PWDF_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_COMPLETION_PARAMS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_COMPLETION_PARAMS</b> structure contains parameters that are associated with the completion of an I/O request.


## -syntax


````
typedef struct _WDF_REQUEST_COMPLETION_PARAMS {
  ULONG            Size;
  WDF_REQUEST_TYPE Type;
  IO_STATUS_BLOCK  IoStatus;
  union {
    struct {
      WDFMEMORY Buffer;
      size_t    Length;
      size_t    Offset;
    } Write;
    struct {
      WDFMEMORY Buffer;
      size_t    Length;
      size_t    Offset;
    } Read;
    struct {
      ULONG  IoControlCode;
      struct {
        WDFMEMORY Buffer;
        size_t    Offset;
      } Input;
      struct {
        WDFMEMORY Buffer;
        size_t    Offset;
        size_t    Length;
      } Output;
    } Ioctl;
    struct {
      union {
        PVOID     Ptr;
        ULONG_PTR Value;
      } Argument1;
      union {
        PVOID     Ptr;
        ULONG_PTR Value;
      } Argument2;
      union {
        PVOID     Ptr;
        ULONG_PTR Value;
      } Argument3;
      union {
        PVOID     Ptr;
        ULONG_PTR Value;
      } Argument4;
    } Others;
    struct {
      PWDF_USB_REQUEST_COMPLETION_PARAMS Completion;
    } Usb;
  } Parameters;
} WDF_REQUEST_COMPLETION_PARAMS, *PWDF_REQUEST_COMPLETION_PARAMS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Type

A <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_type.md">WDF_REQUEST_TYPE</a> value that identifies the request type.


### -field IoStatus

An <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure for the request.


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



###### Ioctl.Input.Buffer

A handle to a framework memory object. This object identifies the input buffer that the driver specified when it formatted the request and sent it to an I/O target.



###### Ioctl.Input.Offset

Beginning address within the buffer for the data transfer.


### -field Parameters.Ioctl.Output



###### Ioctl.Output.Buffer

A handle to a framework memory object. This object identifies the output buffers that the driver specified when it formatted the request and sent it to an I/O target.



###### Ioctl.Output.Offset

Beginning address within the buffer for the data transfer.



###### Ioctl.Output.Length

Length, in bytes, of the transfer.


### -field Parameters.Others


### -field Parameters.Others.Argument1

Use of this member is defined by the driver stack.  See Remarks.


### -field Parameters.Others.Argument2

Use of this member is defined by the driver stack.


### -field Parameters.Others.Argument3

Use of this member is defined by the driver stack.


### -field Parameters.Others.Argument4

Use of this member is defined by the driver stack.


### -field Parameters.Usb

For USB devices, this member contains a pointer to a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_request_completion_params.md">WDF_USB_REQUEST_COMPLETION_PARAMS</a> structure.




### -field Parameters.Usb.Completion

 




## -remarks



The <b>WDF_REQUEST_COMPLETION_PARAMS</b> structure is used as input to the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetcompletionparams.md">WdfRequestGetCompletionParams</a> method and a driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function.

 In both cases, the completion parameters structure contains valid information only if the driver has formatted the request by calling one of the <b>WdfIoTargetFormat</b><i>Xxx</i> methods. For example, see <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforread.md">WdfIoTargetFormatRequestForRead</a>.

Before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetcompletionparams.md">WdfRequestGetCompletionParams</a> to retrieve the I/O completion information for a request, the driver must first call <a href="..\wdfrequest\nf-wdfrequest-wdf_request_completion_params_init.md">WDF_REQUEST_COMPLETION_PARAMS_INIT</a> to initialize the <b>WDF_REQUEST_COMPLETION_PARAMS</b> structure.

The <b>Parameters.Others.Argument</b>  members are custom arguments that a driver typically passes down the stack (and can arrive back after the request is completed).  They are used for non-standard, driver stack dependent data. For example, a USB driver specifies a pointer to a URB in  <b>Parameters.Others.Argument1</b> when it sends a <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_submit_urb.md">IOCTL_INTERNAL_USB_SUBMIT_URB</a> request to the USB stack.  Similarly, a Bluetooth driver specifies a pointer to a  BRB (Bluetooth Request Block) in <b>Parameters.Others.Argument1</b> when it receives an <a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>.




## -see-also


<a href="..\wdfrequest\ne-wdfrequest-_wdf_request_type.md">WDF_REQUEST_TYPE</a>

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_completion_params_init.md">WDF_REQUEST_COMPLETION_PARAMS_INIT</a>



<a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a>



<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetcompletionparams.md">WdfRequestGetCompletionParams</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_COMPLETION_PARAMS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

