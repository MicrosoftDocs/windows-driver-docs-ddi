---
UID: NI:kbdmou.IOCTL_INTERNAL_KEYBOARD_CONNECT
title: IOCTL_INTERNAL_KEYBOARD_CONNECT (kbdmou.h)
description: The IOCTL_INTERNAL_KEYBOARD_CONNECT request connects the Kbdclass service to the keyboard device.
old-location: hid\ioctl_internal_keyboard_connect.htm
tech.root: hid
ms.assetid: 90014194-e790-4b23-9f3d-f5879dd94063
ms.date: 04/30/2018
keywords: ["IOCTL_INTERNAL_KEYBOARD_CONNECT IOCTL"]
ms.keywords: IOCTL_INTERNAL_KEYBOARD_CONNECT, IOCTL_INTERNAL_KEYBOARD_CONNECT control, IOCTL_INTERNAL_KEYBOARD_CONNECT control code [Human Input Devices], hid.ioctl_internal_keyboard_connect, kbdmou/IOCTL_INTERNAL_KEYBOARD_CONNECT, kfilref_b9a87851-bbc4-4567-a459-9e647d6d3315.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_INTERNAL_KEYBOARD_CONNECT
 - kbdmou/IOCTL_INTERNAL_KEYBOARD_CONNECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - kbdmou.h
api_name:
 - IOCTL_INTERNAL_KEYBOARD_CONNECT
---

# IOCTL_INTERNAL_KEYBOARD_CONNECT IOCTL


## -description

The IOCTL_INTERNAL_KEYBOARD_CONNECT request connects the Kbdclass service to the keyboard device. Kbdclass sends this request down the keyboard device stack before it opens the keyboard device. 

After Kbfiltr received the keyboard connect request, Kbfiltr filters the connect request in the following way:

<ul>
<li>
Saves a copy of Kbdclass's <a href="/windows-hardware/drivers/ddi/kbdmou/ns-kbdmou-_connect_data">CONNECT_DATA (Kbdclass)</a> structure that is passed to the filter driver by Kbdclass

</li>
<li>
Substitutes its own connect information for the class driver connect information

</li>
<li>
Sends the IOCTL_INTERNAL_KEYBOARD_CONNECT request down the device stack

</li>
</ul>
If the request is not successful, Kbfiltr completes the request with an appropriate error status.

Kbfiltr provides a template for a filter service callback routine that can supplement the operation of <a href="/previous-versions/ff542324(v=vs.85)">KeyboardClassServiceCallback</a>, the Kbdclass class service callback routine. The filter service callback can filter the input data that is transferred from the device input buffer to the class data queue. 

For more information about the connection of the Kbdclass service, see the following topics:

<dl>
<dd>

<a href="/windows-hardware/drivers/ddi/kbdmou/nc-kbdmou-pservice_callback_routine">Kbdclass Class Service Callback Routine</a>


</dd>
<dd>

<a href="/previous-versions/ff542302(v=vs.85)">Kbfiltr Callback Routines</a>


</dd>
</dl>

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

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the following values:




**STATUS_INVALID_PARAMETER**

<b>


Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of a CONNECT_DATA structure.


**STATUS_SHARING_VIOLATION**



Kbfiltr is already connected (the filter driver supports only one connect request).


**STATUS_SUCCESS**

The request completed successfully.

## -see-also

<a href="/windows-hardware/drivers/ddi/kbdmou/ns-kbdmou-_connect_data">CONNECT_DATA (Kbdclass)</a>



<a href="/windows-hardware/drivers/ddi/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_hook_keyboard">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>



<a href="/previous-versions/ff542324(v=vs.85)">KeyboardClassServiceCallback</a>