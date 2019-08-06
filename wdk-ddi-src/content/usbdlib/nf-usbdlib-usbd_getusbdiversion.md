---
UID: NF:usbdlib.USBD_GetUSBDIVersion
title: USBD_GetUSBDIVersion function (usbdlib.h)
description: The USBD_GetUSBDIVersion routine returns version information about the host controller driver (HCD) that controls the client's USB device.Note  USBD_IsInterfaceVersionSupported replaces the USBD_GetUSBDIVersion routine
old-location: buses\usbd_getusbdiversion.htm
tech.root: usbref
ms.assetid: 47e6da4a-fa81-40ee-9bf5-80526dc0b865
ms.date: 05/07/2018
ms.keywords: USBD_GetUSBDIVersion, USBD_GetUSBDIVersion routine [Buses], buses.usbd_getusbdiversion, usbdlib/USBD_GetUSBDIVersion, usbfunc_567ca75b-8d65-412c-aa28-284a01cff650.xml
ms.topic: function
f1_keywords:
 - "usbdlib/USBD_GetUSBDIVersion"
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
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
req.lib: Usbd.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL (See Remarks)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbd.lib
- Usbd.dll
api_name:
- USBD_GetUSBDIVersion
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_GetUSBDIVersion function


## -description


The <b>USBD_GetUSBDIVersion</b> routine returns version information about the host controller driver (HCD) that controls the client's USB device.
<div class="alert"><b>Note</b>  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_isinterfaceversionsupported">USBD_IsInterfaceVersionSupported</a> replaces the <b>USBD_GetUSBDIVersion</b>  routine</div><div> </div>

## -parameters




### -param VersionInformation [out]

Pointer to caller-allocated memory for a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_usbd_version_information">USBD_VERSION_INFORMATION</a> structure that on return from the routine, contains version information about the HCD.


## -returns



This routine does not return a value.




## -remarks



Callers of this routine can be running at IRQL <= DISPATCH_LEVEL if the memory for <i>VersionInformation</i> is allocated from nonpaged pool. Otherwise, callers must be running at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_usbref/">USB device driver programming reference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_isinterfaceversionsupported">USBD_IsInterfaceVersionSupported</a>
 

 

