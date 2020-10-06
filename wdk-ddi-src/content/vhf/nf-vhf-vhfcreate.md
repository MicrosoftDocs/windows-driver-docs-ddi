---
UID: NF:vhf.VhfCreate
title: VhfCreate function (vhf.h)
description: The HID source driver calls this method to create a virtual HID device.
old-location: hid\vhfcreate.htm
tech.root: hid
ms.assetid: 11A98BBE-2609-4E55-8988-42620EB15281
ms.date: 04/30/2018
keywords: ["VhfCreate function"]
ms.keywords: VhfCreate, VhfCreate method [Human Input Devices], hid.vhfcreate, vhf/VhfCreate
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VhfCreate
 - vhf/VhfCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - vhfKm.lib
 - vhfKm.dll
api_name:
 - VhfCreate
---

# VhfCreate function


## -description

The HID source driver calls this method to create a virtual HID device.

## -parameters

### -param VhfConfig 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> structure.

### -param VhfHandle 

[out]
A handle to the new virtual HID device.

## -returns

If the <b>VhfCreate</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS </a> value.

## -remarks

 This method returns synchronously after validating the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> structure and creating a virtual HID device. The virtual HID device is only reported to PnP. The initialization, installation, and starting of the device may not complete before this method returns.

A Kernel-Mode Driver Framework (KMDF) driver can call <b>VhfCreate</b> at any point after successfully creating its own device object by calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. The driver can do so in its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>.

VHF does not invoke any callback functions that are specified in <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> until the HID source driver calls <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfstart">VhfStart</a>.

## -see-also

<a href="/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>