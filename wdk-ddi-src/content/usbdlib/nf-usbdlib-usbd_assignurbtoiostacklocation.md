---
UID: NF:usbdlib.USBD_AssignUrbToIoStackLocation
title: USBD_AssignUrbToIoStackLocation function
author: windows-driver-content
description: The USBD_AssignUrbToIoStackLocation routine is called by a client driver to associate an URB with the IRP's next stack location.
old-location: buses\usbd_assignurbtostacklocation.htm
tech.root: usbref
ms.assetid: 66A66050-B2BF-47FA-A4E2-BF8816390B16
ms.date: 5/7/2018
ms.keywords: USBD_AssignUrbToIoStackLocation, USBD_AssignUrbToIoStackLocation routine [Buses], buses.usbd_assignurbtostacklocation, usbdlib/USBD_AssignUrbToIoStackLocation
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	USBD_AssignUrbToIoStackLocation
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_AssignUrbToIoStackLocation function


## -description


The <b>USBD_AssignUrbToIoStackLocation</b> routine is called by a client driver to associate an <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> with the IRP's next stack location.


## -parameters




### -param USBDHandle [in]

A USBD handle that is retrieved in a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a> routine.


### -param IoStackLocation [in]

Pointer to the IRP's next stack location (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>). The client driver received a pointer to the stack location in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a>.


### -param Urb [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure that is allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/hh406250">USBD_UrbAllocate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406231">USBD_IsochUrbAllocate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406243">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh406245">USBD_SelectInterfaceUrbAllocateAndBuild</a>.


## -returns



This routine does not return a value.




## -remarks



If the client driver allocated an URB by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh406250">USBD_UrbAllocate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406231">USBD_IsochUrbAllocate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406243">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh406245">USBD_SelectInterfaceUrbAllocateAndBuild</a>, then the driver <i>must</i> call <b>USBD_AssignUrbToIoStackLocation</b> to associate the URB with <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> associated with the IRP. For URBs that are  allocated by those routines, <b>USBD_AssignUrbToIoStackLocation</b> replaces setting   <b>Parameters.Others.Argument1</b> of <b>IO_STACK_LOCATION</b> to the URB. (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537271">IOCTL_INTERNAL_USB_SUBMIT_URB</a>).  

The client driver must <i>not</i> call <b>USBD_AssignUrbToIoStackLocation</b> for an URB that is allocated by using other mechanisms, such as allocating the URB on the stack. Otherwise, the USB driver stack generates a bugcheck.


The client driver must call <b>USBD_AssignUrbToIoStackLocation</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a> to send  the request. <b>USBD_AssignUrbToIoStackLocation</b> populates the IRP's next stack location with the URB.  The routine also updates the <b>FileObject</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>. 

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450899">How to Submit an URB</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450899">How to Submit an URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406231">USBD_IsochUrbAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406243">USBD_SelectConfigUrbAllocateAndBuild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406245">USBD_SelectInterfaceUrbAllocateAndBuild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406250">USBD_UrbAllocate</a>
 

 

