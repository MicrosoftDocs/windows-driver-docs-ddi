---
UID: NF:wdfusb.WDF_USB_DEVICE_INFORMATION_INIT
title: WDF_USB_DEVICE_INFORMATION_INIT function
author: windows-driver-content
description: The WDF_USB_DEVICE_INFORMATION_INIT function initializes a driver's WDF_USB_DEVICE_INFORMATION structure.
old-location: wdf\wdf_usb_device_information_init.htm
old-project: wdf
ms.assetid: 8f4931d7-6b5f-412f-ace9-32f20dfa7c90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_ffde7966-f00b-4614-9845-aaebe2e0488b.xml, WDF_USB_DEVICE_INFORMATION_INIT, WDF_USB_DEVICE_INFORMATION_INIT function, kmdf.wdf_usb_device_information_init, wdf.wdf_usb_device_information_init, wdfusb/WDF_USB_DEVICE_INFORMATION_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_DEVICE_INFORMATION_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_DEVICE_INFORMATION_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_INFORMATION_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552592">WDF_USB_DEVICE_INFORMATION</a> structure.


## -parameters




### -param Udi [out]

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552592">WDF_USB_DEVICE_INFORMATION</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_DEVICE_INFORMATION_INIT</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552592">WDF_USB_DEVICE_INFORMATION</a> structure and sets its <b>Size</b> member to the size of the structure.


#### Examples

For a code example that uses<b>WDF_USB_DEVICE_INFORMATION_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550100">WdfUsbTargetDeviceRetrieveInformation</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552592">WDF_USB_DEVICE_INFORMATION</a>
 

 

