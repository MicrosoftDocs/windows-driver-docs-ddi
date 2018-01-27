---
UID: NF:usbdlib.USBD_AssignUrbToIoStackLocation
title: USBD_AssignUrbToIoStackLocation function
author: windows-driver-content
description: The USBD_AssignUrbToIoStackLocation routine is called by a client driver to associate an URB with the IRP's next stack location.
old-location: buses\usbd_assignurbtostacklocation.htm
old-project: usbref
ms.assetid: 66A66050-B2BF-47FA-A4E2-BF8816390B16
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbdlib/USBD_AssignUrbToIoStackLocation, buses.usbd_assignurbtostacklocation, USBD_AssignUrbToIoStackLocation, USBD_AssignUrbToIoStackLocation routine [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Usbdex.lib
-	Usbdex.dll
apiname: 
-	USBD_AssignUrbToIoStackLocation
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_AssignUrbToIoStackLocation function


## -description


The <b>USBD_AssignUrbToIoStackLocation</b> routine is called by a client driver to associate an <a href="..\usb\ns-usb-_urb.md">URB</a> with the IRP's next stack location.


## -syntax


````
void USBD_AssignUrbToIoStackLocation(
  _In_ USBD_HANDLE        USBDHandle,
  _In_ PIO_STACK_LOCATION StackLocation,
  _In_ PURB               Urb
);
````


## -parameters




### -param USBDHandle [in]

A USBD handle that is retrieved in a previous call to the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.


### -param IoStackLocation

TBD


### -param Urb [in]

Pointer to the <a href="..\usb\ns-usb-_urb.md">URB</a> structure that is allocated by <a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a>, <a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>, <a href="..\usbdlib\nf-usbdlib-usbd_selectconfigurballocateandbuild.md">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="..\usbdlib\nf-usbdlib-usbd_selectinterfaceurballocateandbuild.md">USBD_SelectInterfaceUrbAllocateAndBuild</a>.


#### - StackLocation [in]

Pointer to the IRP's next stack location (<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>). The client driver received a pointer to the stack location in a previous call to <a href="..\wdm\nf-wdm-iogetnextirpstacklocation.md">IoGetNextIrpStackLocation</a>.


## -returns


This routine does not return a value.



## -remarks


If the client driver allocated an URB by calling <a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a>, <a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>, <a href="..\usbdlib\nf-usbdlib-usbd_selectconfigurballocateandbuild.md">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="..\usbdlib\nf-usbdlib-usbd_selectinterfaceurballocateandbuild.md">USBD_SelectInterfaceUrbAllocateAndBuild</a>, then the driver <i>must</i> call <b>USBD_AssignUrbToIoStackLocation</b> to associate the URB with <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> associated with the IRP. For URBs that are  allocated by those routines, <b>USBD_AssignUrbToIoStackLocation</b> replaces setting   <b>Parameters.Others.Argument1</b> of <b>IO_STACK_LOCATION</b> to the URB. (see <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_submit_urb.md">IOCTL_INTERNAL_USB_SUBMIT_URB</a>).  

The client driver must <i>not</i> call <b>USBD_AssignUrbToIoStackLocation</b> for an URB that is allocated by using other mechanisms, such as allocating the URB on the stack. Otherwise, the USB driver stack generates a bugcheck.


The client driver must call <b>USBD_AssignUrbToIoStackLocation</b> before calling <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> to send  the request. <b>USBD_AssignUrbToIoStackLocation</b> populates the IRP's next stack location with the URB.  The routine also updates the <b>FileObject</b> member of <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>. 

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450899">How to Submit an URB</a>.



## -see-also

<a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450899">How to Submit an URB</a>

<a href="..\usbdlib\nf-usbdlib-usbd_selectinterfaceurballocateandbuild.md">USBD_SelectInterfaceUrbAllocateAndBuild</a>

<a href="..\usbdlib\nf-usbdlib-usbd_selectconfigurballocateandbuild.md">USBD_SelectConfigUrbAllocateAndBuild</a>

<a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_AssignUrbToIoStackLocation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

