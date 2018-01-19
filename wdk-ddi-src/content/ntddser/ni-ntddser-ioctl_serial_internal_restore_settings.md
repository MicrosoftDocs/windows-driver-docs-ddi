---
UID: NI:ntddser.IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS
title: IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS
author: windows-driver-content
description: The IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS request restores the specified operating mode of a serial device.
old-location: serports\ioctl_serial_internal_restore_settings.htm
old-project: serports
ms.assetid: 55c56436-ac59-4095-a9f3-f36092db19c0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS
req.alt-loc: ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS IOCTL



## -description

The IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS request restores the specified operating mode of a serial device. The specified operating mode should be a mode that was returned by an <a href="..\ntddser\ni-ntddser-ioctl_serial_internal_basic_settings.md">IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS</a> request. The operating mode settings should be treated as opaque. Serial does not verify the settings when the settings are restored. Note also that a replacement for Serial might implement a different set of parameters.



The IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS request restores the specified operating mode of a serial device. The specified operating mode should be a mode that was returned by an <a href="..\ntddser\ni-ntddser-ioctl_serial_internal_basic_settings.md">IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS</a> request. The operating mode settings should be treated as opaque. Serial does not verify the settings when the settings are restored. Note also that a replacement for Serial might implement a different set of parameters.



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> member of the IRP structure points to a client-allocated SERIAL_BASIC_SETTINGS structure that is used to input operating mode settings. The client should use settings that were returned by an IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IO_STACK_LOCATION structure is set to the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of SERIAL_BASIC_SETTINGS structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>. If Status is set to STATUS_BUFFER_TOO_SMALL, the <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IO_STACK_LOCATION structure is less than the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_internal_basic_settings.md">IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

