---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_HOOK_MOUSE
title: IOCTL_INTERNAL_I8042_HOOK_MOUSE
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_HOOK_MOUSE request adds an ISR callback routine to the I8042prt mouse ISR.
old-location: hid\ioctl_internal_i8042_hook_mouse.htm
old-project: hid
ms.assetid: 606b9ae4-186c-47b1-84aa-3d380eaad672
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: hid.ioctl_internal_i8042_hook_mouse, IOCTL_INTERNAL_I8042_HOOK_MOUSE control code [Human Input Devices], IOCTL_INTERNAL_I8042_HOOK_MOUSE, ntdd8042/IOCTL_INTERNAL_I8042_HOOK_MOUSE, mfilref_d95cd233-bc97-4bd6-8675-2560b83f4715.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdd8042.h
apiname:
-	IOCTL_INTERNAL_I8042_HOOK_MOUSE
product: Windows
targetos: Windows
req.typenames: "*PMOUSE_STATE, MOUSE_STATE"
---

# IOCTL_INTERNAL_I8042_HOOK_MOUSE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_INTERNAL_I8042_HOOK_MOUSE request adds an ISR callback routine to the I8042prt mouse ISR. The ISR callback is optional and is provided by an upper-level mouse filter driver.

I8042prt sends this request after it receives an <a href="..\kbdmou\ni-kbdmou-ioctl_internal_mouse_connect.md">IOCTL_INTERNAL_MOUSE_CONNECT</a> request. I8042prt sends a synchronous IOCTL_INTERNAL_I8042_HOOK_MOUSE request to the top of the mouse device stack.

After Moufiltr receives the hook mouse request, it filters the request in the following way:

<ul>
<li>
Saves the upper-level information passed to Moufiltr, which includes the context of an upper-level device object and a pointer to an ISR callback

</li>
<li>
Replaces the upper-level information with its own

</li>
<li>
Saves the context of I8042prt and pointers to callbacks that the Moufiltr ISR callbacks can use

</li>
</ul>
For more information about this request and the callbacks, see the following topics:

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

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to a value greater than or equal to the size, in bytes, of an <a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_hook_mouse.md">INTERNAL_I8042_HOOK_MOUSE</a> structure.

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an INTERNAL_I8042_HOOK_MOUSE structure that is allocated and set initially by I8042prt.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an INTERNAL_I8042_HOOK_MOUSE structure that is allocated and set initially by I8042prt.


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Status</b> member is set to one of the following values:




#### -STATUS_INVALID_PARAMETER

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of an INTERNAL_I8042_HOOK_MOUSE structure.


#### -STATUS_SUCCESS

The request completed successfully.


## -see-also

<a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_hook_mouse.md">INTERNAL_I8042_HOOK_MOUSE</a>



<a href="..\kbdmou\ni-kbdmou-ioctl_internal_mouse_connect.md">IOCTL_INTERNAL_MOUSE_CONNECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_I8042_HOOK_MOUSE control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

