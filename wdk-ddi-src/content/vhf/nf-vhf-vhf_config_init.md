---
UID: NF:vhf.VHF_CONFIG_INIT
title: VHF_CONFIG_INIT function (vhf.h)
description: Use the VHF_CONFIG_INIT function to initialize the required members of the VHF_CONFIG structure allocated by the HID source driver.
old-location: hid\vhf_config_init.htm
tech.root: hid
ms.date: 10/26/2021
keywords: ["VHF_CONFIG_INIT function"]
ms.keywords: VHF_CONFIG_INIT, VHF_CONFIG_INIT function [Human Input Devices], hid.vhf_config_init, vhf/VHF_CONFIG_INIT
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - VHF_CONFIG_INIT
 - vhf/VHF_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - vhfKm.lib
 - vhfKm.dll
api_name:
 - VHF_CONFIG_INIT
---

# VHF_CONFIG_INIT function


## -description

Use the <b>VHF_CONFIG_INIT</b> function to initialize the required members of the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> structure allocated by the HID source driver.

## -syntax

```cpp
FORCEINLINE
VOID
VHF_CONFIG_INIT(
    _Out_
        PVHF_CONFIG     Config,
#ifdef _KERNEL_MODE
    _In_
        PDEVICE_OBJECT  DeviceObject,
#else
    _In_
        HANDLE          FileHandle,
#endif
    _In_
        USHORT          ReportDescriptorLength,
    _In_reads_bytes_(ReportDescriptorLength)
        PUCHAR          ReportDescriptor    
    )
```

## -parameters

### -param Config [out]


A pointer to the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> structure to initialize.

### -param DeviceObject [in]


A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure for the HID source driver. Get that pointer by calling  <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetdeviceobject">WdfDeviceWdmGetDeviceObject</a> and passing the WDFDEVICE handle that the driver received in the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> call.

A user-mode driver would instead provide a *FileHandle*. For more info, see [**VHF_CONFIG**](./ns-vhf-_vhf_config.md).

### -param ReportDescriptorLength [in]


The length of the HID Report Descriptor contained in a buffer pointer by <i>ReportDescriptor</i>.

### -param ReportDescriptor

A pointer to a HID source driver-allocated buffer that contains the  HID Report Descriptor.

## -see-also

<a href="/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>