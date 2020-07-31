---
UID: NF:usbdlib.USBD_AssignUrbToIoStackLocation
title: USBD_AssignUrbToIoStackLocation function (usbdlib.h)
description: The USBD_AssignUrbToIoStackLocation routine is called by a client driver to associate an URB with the IRP's next stack location.
old-location: buses\usbd_assignurbtostacklocation.htm
tech.root: usbref
ms.assetid: 66A66050-B2BF-47FA-A4E2-BF8816390B16
ms.date: 05/07/2018
keywords: ["USBD_AssignUrbToIoStackLocation function"]
ms.keywords: USBD_AssignUrbToIoStackLocation, USBD_AssignUrbToIoStackLocation routine [Buses], buses.usbd_assignurbtostacklocation, usbdlib/USBD_AssignUrbToIoStackLocation
f1_keywords:
 - "usbdlib/USBD_AssignUrbToIoStackLocation"
 - "USBD_AssignUrbToIoStackLocation"
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbdex.lib
- Usbdex.dll
api_name:
- USBD_AssignUrbToIoStackLocation
targetos: Windows
req.typenames: 
---

# USBD_AssignUrbToIoStackLocation function


## -description


The <b>USBD_AssignUrbToIoStackLocation</b> routine is called by a client driver to associate an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> with the IRP's next stack location.


## -parameters




### -param USBDHandle [in]

A USBD handle that is retrieved in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a> routine.


### -param IoStackLocation [in]

Pointer to the IRP's next stack location (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>). The client driver received a pointer to the stack location in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetnextirpstacklocation">IoGetNextIrpStackLocation</a>.


### -param Urb [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure that is allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_isochurballocate">USBD_IsochUrbAllocate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_selectconfigurballocateandbuild">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_selectinterfaceurballocateandbuild">USBD_SelectInterfaceUrbAllocateAndBuild</a>.


## -remarks



If the client driver allocated an URB by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_isochurballocate">USBD_IsochUrbAllocate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_selectconfigurballocateandbuild">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_selectinterfaceurballocateandbuild">USBD_SelectInterfaceUrbAllocateAndBuild</a>, then the driver <i>must</i> call <b>USBD_AssignUrbToIoStackLocation</b> to associate the URB with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> associated with the IRP. For URBs that are  allocated by those routines, <b>USBD_AssignUrbToIoStackLocation</b> replaces setting   <b>Parameters.Others.Argument1</b> of <b>IO_STACK_LOCATION</b> to the URB. (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_submit_urb">IOCTL_INTERNAL_USB_SUBMIT_URB</a>).  

The client driver must <i>not</i> call <b>USBD_AssignUrbToIoStackLocation</b> for an URB that is allocated by using other mechanisms, such as allocating the URB on the stack. Otherwise, the USB driver stack generates a bugcheck.


The client driver must call <b>USBD_AssignUrbToIoStackLocation</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a> to send  the request. <b>USBD_AssignUrbToIoStackLocation</b> populates the IRP's next stack location with the URB.  The routine also updates the <b>FileObject</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>. 

For a code example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Submit an URB</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Submit an URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_isochurballocate">USBD_IsochUrbAllocate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_selectconfigurballocateandbuild">USBD_SelectConfigUrbAllocateAndBuild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_selectinterfaceurballocateandbuild">USBD_SelectInterfaceUrbAllocateAndBuild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a>
 

 

