---
UID: NF:usbdlib.USBD_ValidateConfigurationDescriptor
title: USBD_ValidateConfigurationDescriptor function (usbdlib.h)
description: The USBD_ValidateConfigurationDescriptor routine validates all descriptors returned by a device in its response to a configuration descriptor request.
old-location: buses\usbd_validateconfigurationdescriptor.htm
tech.root: usbref
ms.assetid: 2fbe08ca-a9eb-4e3b-aa28-1ff34ad22a46
ms.date: 05/07/2018
ms.keywords: USBD_ValidateConfigurationDescriptor, USBD_ValidateConfigurationDescriptor routine [Buses], buses.usbd_validateconfigurationdescriptor, usbdlib/USBD_ValidateConfigurationDescriptor
f1_keywords:
 - "usbdlib/USBD_ValidateConfigurationDescriptor"
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbd.lib
- Usbd.dll
api_name:
- USBD_ValidateConfigurationDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_ValidateConfigurationDescriptor function


## -description


The <b>USBD_ValidateConfigurationDescriptor</b> routine validates all descriptors returned by a device in its response to a configuration descriptor request.


## -parameters




### -param ConfigDesc [in]

Pointer to a configuration descriptor that includes all interface, endpoint, vendor, and class-specific descriptors retrieved from a USB device.  


### -param BufferLength [in]

Size, in bytes, of the configuration descriptor being validated.


### -param Level [in]

Level of validation to be performed.  The following are valid values:

<ul>
<li>1-Basic validation of the configuration descriptor header.</li>
<li>2-Full validation of the configuration descriptor including checking for invalid endpoint addresses, interface numbers, descriptor structures, interface alternate settings, number of interfaces and <b>bLength</b> fields of all descriptors.               
</li>
<li>3-In addition to the validation for levels 1 and 2, level 3 validates plus validates the number of endpoints in each interface, enforces the USB specification's descriptor <b>bLength</b> sizes, and verifies that all interface numbers are in sequential order.</li>
</ul>

### -param Offset [out]

  Offset within configuration descriptor where validation failed.  Only valid when a status other than USBD_STATUS_SUCCESS is returned.


### -param Tag [in, optional]

Pool tag used by <b>USBD_ValidateConfigurationDescriptor</b> when allocating memory.  


## -returns



USBD_STATUS_SUCCESS, or appropriate USBD error code if validation failed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>
 

 

