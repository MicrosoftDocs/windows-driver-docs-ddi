---
UID: NF:vhf.VhfCreate
title: VhfCreate function (vhf.h)
description: The HID source driver calls this method to create a virtual HID device.
old-location: hid\vhfcreate.htm
tech.root: hid
ms.assetid: 11A98BBE-2609-4E55-8988-42620EB15281
ms.date: 04/30/2018
ms.keywords: VhfCreate, VhfCreate method [Human Input Devices], hid.vhfcreate, vhf/VhfCreate
ms.topic: function
req.header: vhf.h
req.include-header: 
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
req.lib: VhfKm.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	vhfKm.lib
-	vhfKm.dll
api_name:
-	VhfCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# VhfCreate function


## -description


The HID source driver calls this method to create a virtual HID device.


## -parameters




### -param VhfConfig [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925044">VHF_CONFIG</a> structure.


### -param VhfHandle [out]

A handle to the new virtual HID device.


## -returns



If the <b>VhfCreate</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.




## -remarks



 This method returns synchronously after validating the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925044">VHF_CONFIG</a> structure and creating a virtual HID device. The virtual HID device is only reported to PnP. The initialization, installation, and starting of the device may not complete before this method returns.

A Kernel-Mode Driver Framework (KMDF) driver can call <b>VhfCreate</b> at any point after successfully creating its own device object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. The driver can do so in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>, <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>, <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>, <a href="https://msdn.microsoft.com/9dbc66db-ea94-4e6a-9618-00999a9dd641">EvtDeviceSelfManagedIoInit</a>.

VHF does not invoke any callback functions that are specified in <a href="https://msdn.microsoft.com/library/windows/hardware/dn925044">VHF_CONFIG</a> until the HID source driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/dn925042">VhfStart</a>.




## -see-also




<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

