---
UID: NS:hidport._HID_MINIDRIVER_REGISTRATION
title: "_HID_MINIDRIVER_REGISTRATION"
author: windows-driver-content
description: The HID_MINIDRIVER_REGISTRATION structure contains registration information that a HID minidriver passes to the HID Client Drivers when the minidriver registers with the class driver.
old-location: hid\hid_minidriver_registration.htm
old-project: hid
ms.assetid: 75c0f546-1a58-45e8-a3eb-3075f07c426b
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: PHID_MINIDRIVER_REGISTRATION, hidport/PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION, _HID_MINIDRIVER_REGISTRATION, PHID_MINIDRIVER_REGISTRATION structure pointer [Human Input Devices], *PHID_MINIDRIVER_REGISTRATION, hidstrct_d0f637a8-58c0-4d83-9a2f-2e14761b6183.xml, hid.hid_minidriver_registration, HID_MINIDRIVER_REGISTRATION structure [Human Input Devices], hidport/HID_MINIDRIVER_REGISTRATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidport.h
req.include-header: Hidport.h
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
-	hidport.h
apiname:
-	HID_MINIDRIVER_REGISTRATION
product: Windows
targetos: Windows
req.typenames: "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION"
---

# _HID_MINIDRIVER_REGISTRATION structure


## -description


The HID_MINIDRIVER_REGISTRATION structure contains registration information that a HID minidriver passes to the <a href="https://msdn.microsoft.com/E7C57273-B661-4B82-816E-E1466DAF67EA">HID Client Drivers</a> when the minidriver registers with the class driver.


## -syntax


````
typedef struct _HID_MINIDRIVER_REGISTRATION {
  ULONG           Revision;
  PDRIVER_OBJECT  DriverObject;
  PUNICODE_STRING RegistryPath;
  ULONG           DeviceExtensionSize;
  BOOLEAN         DevicesArePolled;
  UCHAR           Reserved[3];
} HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION;
````


## -struct-fields




#### - Revision

Specifies the HID version that this minidriver supports.


#### - DriverObject

Pointer to the minidriver's <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>.


#### - RegistryPath

Pointer to the minidriver's registry path.


#### - DeviceExtensionSize

Specifies the length, in bytes, that the minidriver requests for a device extension.


#### - DevicesArePolled

Specifies that the devices on the bus that this minidriver supports must be polled in order to obtain data from the device.


#### - Reserved

Reserved for internal system use.


## -remarks


When a HID minidriver calls <a href="..\hidport\nf-hidport-hidregisterminidriver.md">HidRegisterMinidriver</a>, it uses this structure to pass information to the HID class driver. The minidriver must must zero-initialize this structure before setting members. A minidriver sets the members <b>DriverObject</b> and <b>RegistryPath</b> to the driver object and registry path parameters that are passed to the minidriver as system-supplied parameters to its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. <b>Revision</b> should be set to HID_REVISION.



## -see-also

<a href="..\hidport\nf-hidport-hidregisterminidriver.md">HidRegisterMinidriver</a>

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HID_MINIDRIVER_REGISTRATION structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

