---
UID: NF:hidsdi.HidD_GetNumInputBuffers
title: HidD_GetNumInputBuffers function
author: windows-driver-content
description: The HidD_GetNumInputBuffers routine returns the current size, in number of reports, of the ring buffer that the HID class driver uses to queue input reports from a specified top-level collection.
old-location: hid\hidd_getnuminputbuffers.htm
old-project: hid
ms.assetid: f9ed28a5-835c-47c8-b9cf-888785013b69
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidD_GetNumInputBuffers, HidD_GetNumInputBuffers routine [Human Input Devices], hidsdi/HidD_GetNumInputBuffers, hidfunc_addf7040-0b62-45bc-8b43-1aa0157924e8.xml, hid.hidd_getnuminputbuffers
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hid.dll
apiname:
-	HidD_GetNumInputBuffers
product: Windows
targetos: Windows
req.typenames: "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION"
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetNumInputBuffers routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

