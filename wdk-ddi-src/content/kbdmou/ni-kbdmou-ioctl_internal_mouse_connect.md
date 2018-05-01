---
UID: NI:kbdmou.IOCTL_INTERNAL_MOUSE_CONNECT
title: IOCTL_INTERNAL_MOUSE_CONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_MOUSE_CONNECT request connects Mouclass service to a mouse device.
old-location: hid\ioctl_internal_mouse_connect.htm
old-project: hid
ms.assetid: f20e424a-60d3-4bfa-9cc3-d2541c927b22
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_MOUSE_CONNECT, IOCTL_INTERNAL_MOUSE_CONNECT control, IOCTL_INTERNAL_MOUSE_CONNECT control code [Human Input Devices], hid.ioctl_internal_mouse_connect, kbdmou/IOCTL_INTERNAL_MOUSE_CONNECT, mfilref_df1ebbe7-9806-4c2a-93c5-4fcbbfdf2f1f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: kbdmou.h
req.include-header: Kbdmou.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	kbdmou.h
api_name:
-	IOCTL_INTERNAL_MOUSE_CONNECT
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_MOUSE_CONNECT IOCTL


## -description


The IOCTL_INTERNAL_MOUSE_CONNECT request connects Mouclass service to a mouse device. Mouclass sends this request down the device stack before it opens a mouse device. 

After Moufiltr receives the mouse connect request, it filters the request in the following way:
<ol>
<li>
Saves a copy of the <a href="https://msdn.microsoft.com/c6c2ebe5-eb88-4dc6-a85a-b297ecdc85d3">CONNECT_DATA (Mouclass)</a> structure that was passed to Moufiltr

</li>
<li>
Substitutes its own connect information for the class driver connect information

</li>
<li>
Sends the IOCTL_INTERNAL_MOUSE_CONNECT request down the device stack

</li>
</ol>If the request is not successful, Moufiltr completes the request with an appropriate error status.

Moufiltr provides a template for a filter service callback routine that can supplement the operation of <a href="https://msdn.microsoft.com/949955c1-a1c7-4b0b-a74e-593dd7885135">MouseClassServiceCallback</a>, the Mouclass service callback routine. The filter service callback can filter the input data that is transferred from the device input buffer to the class driver data queue. 

For more information about the connection of the Mouclass service, see the following topics:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539965">I8042prt Callback Routines</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/c6b60905-edd0-496e-a4e7-5ca271a51bce">Moufiltr Callback Routines</a>


</dd>
</dl>

## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> member points to a CONNECT_DATA structure that is allocated and set by Mouclass.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to a value greater than or equal to the size, in bytes, of a CONNECT_DATA structure.


### -output-buffer

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> member points to a CONNECT_DATA structure that is set by Moufiltr.


### -output-buffer-length

The size of a CONNECT_DATA structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the following values:




#### -STATUS_INVALID_PARAMETER

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of a CONNECT_DATA structure.


#### -STATUS_SHARING_VIOLATION

Moufiltr is already connected (a filter driver supports only one connect request).


## -see-also




<a href="https://msdn.microsoft.com/c6c2ebe5-eb88-4dc6-a85a-b297ecdc85d3">CONNECT_DATA (Mouclass)</a>



<a href="https://msdn.microsoft.com/949955c1-a1c7-4b0b-a74e-593dd7885135">MouseClassServiceCallback</a>
 

 

