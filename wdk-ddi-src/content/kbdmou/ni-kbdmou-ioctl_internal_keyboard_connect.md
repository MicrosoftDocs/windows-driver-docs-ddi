---
UID: NI:kbdmou.IOCTL_INTERNAL_KEYBOARD_CONNECT
title: IOCTL_INTERNAL_KEYBOARD_CONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_KEYBOARD_CONNECT request connects the Kbdclass service to the keyboard device.
old-location: hid\ioctl_internal_keyboard_connect.htm
old-project: hid
ms.assetid: 90014194-e790-4b23-9f3d-f5879dd94063
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _MSiSCSI_SessionStatistics, MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics
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
req.alt-api: IOCTL_INTERNAL_KEYBOARD_CONNECT
req.alt-loc: kbdmou.h
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
req.typenames: MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics
---

# IOCTL_INTERNAL_KEYBOARD_CONNECT IOCTL



## -description

The IOCTL_INTERNAL_KEYBOARD_CONNECT request connects the Kbdclass service to the keyboard device. Kbdclass sends this request down the keyboard device stack before it opens the keyboard device. 

After Kbfiltr received the keyboard connect request, Kbfiltr filters the connect request in the following way:

<ul>
<li>
Saves a copy of Kbdclass's <a href="..\kbdmou\ns-kbdmou-_connect_data.md">CONNECT_DATA (Kbdclass)</a> structure that is passed to the filter driver by Kbdclass

</li>
<li>
Substitutes its own connect information for the class driver connect information

</li>
<li>
Sends the IOCTL_INTERNAL_KEYBOARD_CONNECT request down the device stack

</li>
</ul>
If the request is not successful, Kbfiltr completes the request with an appropriate error status.

Kbfiltr provides a template for a filter service callback routine that can supplement the operation of <a href="https://msdn.microsoft.com/02815805-47cf-454c-8117-f5686a855e25">KeyboardClassServiceCallback</a>, the Kbdclass class service callback routine. The filter service callback can filter the input data that is transferred from the device input buffer to the class data queue. 

For more information about the connection of the Kbdclass service, see the following topics:

<dl>
<dd>

<a href="..\kbdmou\nc-kbdmou-pservice_callback_routine.md">Kbdclass Class Service Callback Routine</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/a939a2f1-740d-4d6e-a908-cfbefc0808a2">Kbfiltr Callback Routines</a>


</dd>
</dl>


The IOCTL_INTERNAL_KEYBOARD_CONNECT request connects the Kbdclass service to the keyboard device. Kbdclass sends this request down the keyboard device stack before it opens the keyboard device. 

After Kbfiltr received the keyboard connect request, Kbfiltr filters the connect request in the following way:

Saves a copy of Kbdclass's <a href="..\kbdmou\ns-kbdmou-_connect_data.md">CONNECT_DATA (Kbdclass)</a> structure that is passed to the filter driver by Kbdclass

Substitutes its own connect information for the class driver connect information

Sends the IOCTL_INTERNAL_KEYBOARD_CONNECT request down the device stack

If the request is not successful, Kbfiltr completes the request with an appropriate error status.

Kbfiltr provides a template for a filter service callback routine that can supplement the operation of <a href="https://msdn.microsoft.com/02815805-47cf-454c-8117-f5686a855e25">KeyboardClassServiceCallback</a>, the Kbdclass class service callback routine. The filter service callback can filter the input data that is transferred from the device input buffer to the class data queue. 

For more information about the connection of the Kbdclass service, see the following topics:


<a href="..\kbdmou\nc-kbdmou-pservice_callback_routine.md">Kbdclass Class Service Callback Routine</a>



<a href="https://msdn.microsoft.com/a939a2f1-740d-4d6e-a908-cfbefc0808a2">Kbfiltr Callback Routines</a>




## -ioctlparameters

### -input-buffer
The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> member points to a <b>CONNECT_DATA</b> structure that is allocated and set by Kbdclass.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to a value greater than or equal to the size, in bytes, of a CONNECT_DATA structure.


### -output-buffer
The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> member points to a <b>CONNECT_DATA</b> structure that is set by Kbfiltr.


### -output-buffer-length
The size of a <b>CONNECT_DATA</b> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the following values:



The request completed successfully.

<b>


Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of a CONNECT_DATA structure.



Kbfiltr is already connected (the filter driver supports only one connect request).


## -remarks


## -see-also
<dl>
<dt>
<a href="..\kbdmou\ns-kbdmou-_connect_data.md">CONNECT_DATA (Kbdclass)</a>
</dt>
<dt>
<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/02815805-47cf-454c-8117-f5686a855e25">KeyboardClassServiceCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_KEYBOARD_CONNECT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

