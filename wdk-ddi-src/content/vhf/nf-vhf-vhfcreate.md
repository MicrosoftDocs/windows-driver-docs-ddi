---
UID: NF:vhf.VhfCreate
title: VhfCreate function
author: windows-driver-content
description: The HID source driver calls this method to create a virtual HID device.
old-location: hid\vhfcreate.htm
old-project: hid
ms.assetid: 11A98BBE-2609-4E55-8988-42620EB15281
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: VhfCreate, hid.vhfcreate, vhf/VhfCreate, VhfCreate method [Human Input Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	vhfKm.lib
-	vhfKm.dll
apiname: 
-	VhfCreate
product: Windows
targetos: Windows
req.typenames: *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---

# VhfCreate function


## -description


The HID source driver calls this method to create a virtual HID device.


## -syntax


````
NTSTATUS VhfCreate(
  [in]  PVHF_CONFIG VhfConfig,
  [out] VHFHANDLE   *VhfHandle
);
````


## -parameters




### -param VhfConfig [in]

A pointer to a <a href="..\vhf\ns-vhf-_vhf_config.md">VHF_CONFIG</a> structure.


### -param VhfHandle [out]

A handle to the new virtual HID device.


## -returns


If the <b>VhfCreate</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.



## -remarks


 This method returns synchronously after validating the <a href="..\vhf\ns-vhf-_vhf_config.md">VHF_CONFIG</a> structure and creating a virtual HID device. The virtual HID device is only reported to PnP. The initialization, installation, and starting of the device may not complete before this method returns.

A Kernel-Mode Driver Framework (KMDF) driver can call <b>VhfCreate</b> at any point after successfully creating its own device object by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. The driver can do so in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>, <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>, <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>, <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>.

VHF does not invoke any callback functions that are specified in <a href="..\vhf\ns-vhf-_vhf_config.md">VHF_CONFIG</a> until the HID source driver calls <a href="..\vhf\nf-vhf-vhfstart.md">VhfStart</a>.



## -see-also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20VhfCreate method%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

