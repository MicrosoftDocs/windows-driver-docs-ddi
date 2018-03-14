---
UID: NF:hidsdi.HidD_GetNumInputBuffers
title: HidD_GetNumInputBuffers function
author: windows-driver-content
description: The HidD_GetNumInputBuffers routine returns the current size, in number of reports, of the ring buffer that the HID class driver uses to queue input reports from a specified top-level collection.
old-location: hid\hidd_getnuminputbuffers.htm
old-project: hid
ms.assetid: f9ed28a5-835c-47c8-b9cf-888785013b69
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidD_GetNumInputBuffers, HidD_GetNumInputBuffers routine [Human Input Devices], hid.hidd_getnuminputbuffers, hidfunc_addf7040-0b62-45bc-8b43-1aa0157924e8.xml, hidsdi/HidD_GetNumInputBuffers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hid.dll
api_name:
-	HidD_GetNumInputBuffers
product: Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_GetNumInputBuffers function


## -description


The <b>HidD_GetNumInputBuffers</b> routine returns the current size, in number of reports, of the ring buffer that the HID class driver uses to queue input reports from a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -syntax


````
BOOLEAN __stdcall HidD_GetNumInputBuffers(
  _In_  HANDLE HidDeviceObject,
  _Out_ PULONG NumberBuffers
);
````


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param NumberBuffers [out]

Pointer to a caller-allocated variable that the routine uses to return the maximum number of input reports the ring buffer can hold.


## -returns



<b>HidD_GetNumInputBuffers</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_GetNumInputBuffers</b>. Kernel-mode drivers can use the <a href="..\hidclass\ni-hidclass-ioctl_get_num_device_input_buffers.md">IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS</a> request.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also

<a href="..\hidsdi\nf-hidsdi-hidd_setnuminputbuffers.md">HidD_SetNumInputBuffers</a>



<a href="..\hidclass\ni-hidclass-ioctl_set_num_device_input_buffers.md">IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS</a>



<a href="..\hidclass\ni-hidclass-ioctl_get_num_device_input_buffers.md">IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS</a>



 

 


