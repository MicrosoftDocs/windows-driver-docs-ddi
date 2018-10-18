---
UID: NF:usbdlib.USBD_ParseConfigurationDescriptor
title: USBD_ParseConfigurationDescriptor function
author: windows-driver-content
description: The USBD_ParseConfigurationDescriptor routine has been deprecated. Use USBD_ParseConfigurationDescriptorEx instead.
old-location: buses\usbd_parseconfigurationdescriptor.htm
tech.root: usbref
ms.assetid: a82816d8-2516-4bba-a5aa-0154cd079d5b
ms.date: 5/7/2018
ms.keywords: USBD_ParseConfigurationDescriptor, USBD_ParseConfigurationDescriptor routine [Buses], buses.usbd_parseconfigurationdescriptor, usbdlib/USBD_ParseConfigurationDescriptor, usbfunc_e0bfa26f-42a8-47a2-bf0e-5f8c97c5e9eb.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbd.lib
-	Usbd.dll
api_name:
-	USBD_ParseConfigurationDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_ParseConfigurationDescriptor function


## -description


The  <b>USBD_ParseConfigurationDescriptor</b> routine has been deprecated. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539102">USBD_ParseConfigurationDescriptorEx</a> instead.


## -parameters




### -param ConfigurationDescriptor [in]

Pointer to a USB configuration descriptor that contains the interface for which to search.


### -param InterfaceNumber [in]

Specifies the device-defined index of the interface to be retrieved. This should be set to -1 if it should not be a search criterion.


### -param AlternateSetting [in]

Specifies the device-defined alternate-setting index of the interface to be retrieved. If the caller does not wish the alternate setting value to be a search criterion, this parameter should be set to -1.


## -returns



<b>USBD_ParseConfigurationDescriptor</b> returns a pointer to the first interface descriptor that matches the given search criteria. If no interface matches the search criteria, it returns <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539102">USBD_ParseConfigurationDescriptorEx</a>
 

 

