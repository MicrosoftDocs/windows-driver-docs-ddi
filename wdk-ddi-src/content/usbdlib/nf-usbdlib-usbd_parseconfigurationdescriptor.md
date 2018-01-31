---
UID: NF:usbdlib.USBD_ParseConfigurationDescriptor
title: USBD_ParseConfigurationDescriptor function
author: windows-driver-content
description: The USBD_ParseConfigurationDescriptor routine has been deprecated. Use USBD_ParseConfigurationDescriptorEx instead.
old-location: buses\usbd_parseconfigurationdescriptor.htm
old-project: usbref
ms.assetid: a82816d8-2516-4bba-a5aa-0154cd079d5b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_ParseConfigurationDescriptor routine [Buses], usbdlib/USBD_ParseConfigurationDescriptor, buses.usbd_parseconfigurationdescriptor, USBD_ParseConfigurationDescriptor, usbfunc_e0bfa26f-42a8-47a2-bf0e-5f8c97c5e9eb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated. Use USBD_ParseConfigurationDescriptorEx instead.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbd.lib
-	Usbd.dll
apiname:
-	USBD_ParseConfigurationDescriptor
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_ParseConfigurationDescriptor function


## -description


The  <b>USBD_ParseConfigurationDescriptor</b> routine has been deprecated. Use <a href="..\usbdlib\nf-usbdlib-usbd_parseconfigurationdescriptorex.md">USBD_ParseConfigurationDescriptorEx</a> instead.


## -syntax


````
PUSB_INTERFACE_DESCRIPTOR USBD_ParseConfigurationDescriptor(
  _In_ PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _In_ UCHAR                         InterfaceNumber,
  _In_ UCHAR                         AlternateSetting
);
````


## -parameters




#### - ConfigurationDescriptor [in]

Pointer to a USB configuration descriptor that contains the interface for which to search.


#### - InterfaceNumber [in]

Specifies the device-defined index of the interface to be retrieved. This should be set to -1 if it should not be a search criterion.


#### - AlternateSetting [in]

Specifies the device-defined alternate-setting index of the interface to be retrieved. If the caller does not wish the alternate setting value to be a search criterion, this parameter should be set to -1.


## -returns


<b>USBD_ParseConfigurationDescriptor</b> returns a pointer to the first interface descriptor that matches the given search criteria. If no interface matches the search criteria, it returns <b>NULL</b>.



## -see-also

<a href="..\usbdlib\nf-usbdlib-usbd_parseconfigurationdescriptorex.md">USBD_ParseConfigurationDescriptorEx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ParseConfigurationDescriptor routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

