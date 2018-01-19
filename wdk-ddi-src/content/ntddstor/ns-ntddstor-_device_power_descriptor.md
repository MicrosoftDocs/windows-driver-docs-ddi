---
UID: NS:ntddstor._DEVICE_POWER_DESCRIPTOR
title: _DEVICE_POWER_DESCRIPTOR
author: windows-driver-content
description: Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY control code to describes the power capabilities of a storage device.
old-location: storage\device_power_descriptor.htm
old-project: storage
ms.assetid: A5925EE4-768C-421A-9813-015513751A91
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEVICE_POWER_DESCRIPTOR, *PDEVICE_POWER_DESCRIPTOR, DEVICE_POWER_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVICE_POWER_DESCRIPTOR
req.alt-loc: ntddstor.h
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
req.typenames: *PDEVICE_POWER_DESCRIPTOR, DEVICE_POWER_DESCRIPTOR
---

# _DEVICE_POWER_DESCRIPTOR structure



## -description
Used in conjunction with the 
   <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> control code 
   to describes the power capabilities of a storage device.



## -syntax

````
typedef struct _DEVICE_POWER_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  BOOLEAN DeviceAttentionSupported;
  BOOLEAN AsynchronousNotificationSupported;
  BOOLEAN IdlePowerManagementEnabled;
  BOOLEAN D3ColdEnabled;
  BOOLEAN D3ColdSupported;
  BOOLEAN NoVerifyDuringIdlePower;
  UCHAR   Reserved[2];
  ULONG   IdleTimeoutInMS;
} DEVICE_POWER_DESCRIPTOR, *PDEVICE_POWER_DESCRIPTOR;
````


## -struct-fields

### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to 
      the structure.


### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.


### -field DeviceAttentionSupported

<b>True</b> if device attention is supported. Otherwise, <b>False</b>.


### -field AsynchronousNotificationSupported

<b>True</b> if the device supports asynchronous notifications, delivered via 
      <b>IOCTL_STORAGE_EVENT_NOTIFICATION</b>. Otherwise, <b>False</b>


### -field IdlePowerManagementEnabled

<b>True</b> if the device has been registered for runtime idle power management. Otherwise, <b>False</b>


### -field D3ColdEnabled

<b>True</b> if the device will be powered off when put into the D3 power state. Otherwise, <b>False</b>


### -field D3ColdSupported

<b>True</b> if the platform supports <b>D3ColdEnabled</b> for this device. Otherwise, 
      <b>False</b>.


### -field NoVerifyDuringIdlePower

<b>True</b> if the device requires no verification during idle power transitions. Otherwise, <b>False</b>


### -field Reserved

Reserved.


### -field IdleTimeoutInMS

The idle timeout value in milliseconds. This member is ignored unless 
      <b>IdlePowerManagementEnabled</b> is true.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_POWER_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

