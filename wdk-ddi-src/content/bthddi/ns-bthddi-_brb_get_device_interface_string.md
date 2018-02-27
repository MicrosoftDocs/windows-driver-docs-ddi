---
UID: NS:bthddi._BRB_GET_DEVICE_INTERFACE_STRING
title: "_BRB_GET_DEVICE_INTERFACE_STRING"
author: windows-driver-content
description: The _BRB_GET_DEVICE_INTERFACE_STRING structure describes the device interface string for the current device object.
old-location: bltooth\_brb_get_device_interface_string.htm
old-project: bltooth
ms.assetid: 340e4b9a-9959-4eda-b26b-674f7fca7156
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_GET_DEVICE_INTERFACE_STRING, _BRB_GET_DEVICE_INTERFACE_STRING structure [Bluetooth Devices], bltooth._brb_get_device_interface_string, bth_structs_3d85c9ac-2714-4d6c-8a3e-f8908d8e5be9.xml, bthddi/_BRB_GET_DEVICE_INTERFACE_STRING"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_GET_DEVICE_INTERFACE_STRING
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_GET_DEVICE_INTERFACE_STRING structure


## -description


The _BRB_GET_DEVICE_INTERFACE_STRING structure describes the device interface string for the current
  device object.


## -syntax


````
struct _BRB_GET_DEVICE_INTERFACE_STRING {
  BRB_HEADER Hdr;
  PWCHAR     DeviceInterfaceString;
  ULONG      DeviceInterfaceStringCbLength;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field DeviceInterfaceString

A pointer to the buffer to contain the device interface string.


### -field DeviceInterfaceStringCbLength

On input, this member specifies the length, in bytes, of the device interface string. On output,
     this member specifies the number of bytes required for the string if the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536856">
     BRB_GET_DEVICE_INTERFACE_STRING</a> BRB fails and returns STATUS_MORE_ENTRIES because of insufficient
     buffer length. If the BRB call succeeds, this member contains the number of bytes copied.


## -remarks



To get the device interface string for the current device object, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536856">
    BRB_GET_DEVICE_INTERFACE_STRING</a> request.

The Bluetooth driver stack performs an 
    <a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a> call on
    each device object it creates. The BRB returns the device interface string returned by that call. This
    can be useful for registering for events.

If the buffer pointed to by the 
    <b>DeviceInterfaceString</b> member is not large enough to hold the string, the call fails and the 
    <b>DeviceInterfaceStringCbLength</b> member contains the required buffer length.




## -see-also

<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



<a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536856">
   BRB_GET_DEVICE_INTERFACE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_GET_DEVICE_INTERFACE_STRING structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

