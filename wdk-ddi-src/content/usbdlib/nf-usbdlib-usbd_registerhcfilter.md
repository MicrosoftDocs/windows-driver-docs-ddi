---
UID: NF:usbdlib.USBD_RegisterHcFilter
title: USBD_RegisterHcFilter function
author: windows-driver-content
description: The USBD_RegisterHcFilter routine has been deprecated in Windows XP and later operating systems.
old-location: buses\usbd_registerhcfilter.htm
old-project: usbref
ms.assetid: 2cc24024-75ec-45ba-867c-efc8e7da7587
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_RegisterHcFilter, USBD_RegisterHcFilter routine [Buses], buses.usbd_registerhcfilter, usbdlib/USBD_RegisterHcFilter, usbfunc_de494163-188c-4356-bd91-c6fa38693d55.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbd.lib
-	Usbd.dll
apiname:
-	USBD_RegisterHcFilter
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_RegisterHcFilter function


## -description


The <b>USBD_RegisterHcFilter</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 

On  Windows XP and later operating systems, a filter driver that is installed between the root hub FDO and PDO sees all USB traffic for a USB device after it has been enumerated.  There is no supported mechanism for filtering descriptor requests that occur during the enumeration of a USB device, because those requests originate and remain in the port driver (usbport.sys) and not the hub driver.


## -syntax


````
VOID USBD_RegisterHcFilter(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PDEVICE_OBJECT FilterDeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object that is the current top of the stack as reported by <a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>.


### -param FilterDeviceObject [in]

Pointer to the filter device object created by the filter driver for its operations.


## -returns



None. 




## -remarks



USB bus filter drivers must call this routine after attaching their device object to the device object stack for the host controller driver.




## -see-also

<a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_RegisterHcFilter routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

