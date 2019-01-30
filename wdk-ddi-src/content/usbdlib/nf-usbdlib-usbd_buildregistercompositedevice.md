---
UID: NF:usbdlib.USBD_BuildRegisterCompositeDevice
title: USBD_BuildRegisterCompositeDevice function (usbdlib.h)
description: The USBD_BuildRegisterCompositeDevice routine is called by the driver of a USB multi-function device (composite driver) to initialize a REGISTER_COMPOSITE_DEVICE structure with the information required for registering the driver with the USB driver stack.
old-location: buses\usbd_buildregistercompositedriver.htm
tech.root: usbref
ms.assetid: 6683C688-CCDD-498B-AA60-81430DC3BCA4
ms.date: 05/07/2018
ms.keywords: USBD_BuildRegisterCompositeDevice, USBD_BuildRegisterCompositeDevice routine [Buses], buses.usbd_buildregistercompositedriver, usbdlib/ USBD_BuildRegisterCompositeDevice
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
req.irql: "< = DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	USBD_BuildRegisterCompositeDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_BuildRegisterCompositeDevice function


## -description


The <b>USBD_BuildRegisterCompositeDevice</b> routine is called by the driver of a USB  multi-function device (composite driver) to  initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a> structure with the information required for registering the driver with the USB driver stack. 

The routine is called by a driver that replaces the Microsoft-provided composite driver, Usbccgp.sys.


## -parameters




### -param USBDHandle [in]

A USBD handle that is retrieved in a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a> routine.


### -param CapabilityFlags [in]

A caller-allocated <a href="https://msdn.microsoft.com/3C1BF8C6-3489-4636-9B3F-B0C2C1327466">COMPOSITE_DEVICE_CAPABILITIES</a> structure that indicates the capabilities that are supported by the composite driver. For instance, to   indicate that the composite driver supports function suspend, set the <b>CapabilityFunctionSuspend</b> member of <b>COMPOSITE_DEVICE_CAPABILITIES</b> to 1.


### -param FunctionCount [in]

The number of physical device objects (PDOs) to be created by the parent driver. The <i>FunctionCount</i> value cannot exceed 255.


### -param RegisterCompositeDevice [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a> structure. Upon completion, the structure is populated with the specified registration  information. To register the composite driver, send the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> I/O request and pass the populated structure. 


## -returns



This routine does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a>
 

 

