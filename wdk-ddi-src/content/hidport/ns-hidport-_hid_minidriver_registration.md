---
UID: NS:hidport._HID_MINIDRIVER_REGISTRATION
title: _HID_MINIDRIVER_REGISTRATION (hidport.h)
description: The HID_MINIDRIVER_REGISTRATION structure contains registration information that a HID minidriver passes to the HID Client Drivers when the minidriver registers with the class driver.
old-location: hid\hid_minidriver_registration.htm
tech.root: hid
ms.assetid: 75c0f546-1a58-45e8-a3eb-3075f07c426b
ms.date: 04/30/2018
keywords: ["_HID_MINIDRIVER_REGISTRATION structure"]
ms.keywords: "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION structure [Human Input Devices], PHID_MINIDRIVER_REGISTRATION, PHID_MINIDRIVER_REGISTRATION structure pointer [Human Input Devices], _HID_MINIDRIVER_REGISTRATION, hid.hid_minidriver_registration, hidport/HID_MINIDRIVER_REGISTRATION, hidport/PHID_MINIDRIVER_REGISTRATION, hidstrct_d0f637a8-58c0-4d83-9a2f-2e14761b6183.xml"
f1_keywords:
 - "hidport/HID_MINIDRIVER_REGISTRATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hidport.h
api_name:
- HID_MINIDRIVER_REGISTRATION
product:
- Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# _HID_MINIDRIVER_REGISTRATION structure


## -description


The HID_MINIDRIVER_REGISTRATION structure contains registration information that a HID minidriver passes to the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-client-drivers">HID Client Drivers</a> when the minidriver registers with the class driver.


## -struct-fields




### -field Revision

Specifies the HID version that this minidriver supports.


### -field DriverObject

Pointer to the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>.


### -field RegistryPath

Pointer to the minidriver's registry path.


### -field DeviceExtensionSize

Specifies the length, in bytes, that the minidriver requests for a device extension.


### -field DevicesArePolled

Specifies that the devices on the bus that this minidriver supports must be polled in order to obtain data from the device.


### -field Reserved

Reserved for internal system use.


## -remarks



When a HID minidriver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidport/nf-hidport-hidregisterminidriver">HidRegisterMinidriver</a>, it uses this structure to pass information to the HID class driver. The minidriver must zero-initialize this structure before setting members. A minidriver sets the members <b>DriverObject</b> and <b>RegistryPath</b> to the driver object and registry path parameters that are passed to the minidriver as system-supplied parameters to its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. <b>Revision</b> should be set to HID_REVISION.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidport/nf-hidport-hidregisterminidriver">HidRegisterMinidriver</a>
 

 

