---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function (wdfiotarget.h)
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so that the driver can open a remote I/O target by specifying a Windows Driver Model (WDM) device object.
old-location: wdf\wdf_io_target_open_params_init_existing_device.htm
tech.root: wdf
ms.assetid: 41fc4479-98e4-4632-89a1-1638eff02279
ms.date: 02/26/2018
keywords: ["WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function"]
ms.keywords: DFIOTargetRef_fdd5195f-e259-4c89-b55e-e6ad06492a4d.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE, WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function, kmdf.wdf_io_target_open_params_init_existing_device, wdf.wdf_io_target_open_params_init_existing_device, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE
 - wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfiotarget.h
api_name:
 - WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure so that the driver can open a remote I/O target by specifying a Windows Driver Model (WDM) device object.

## -parameters

### -param Params 

[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure that the function initializes.

### -param DeviceObject 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure, which is used as the value for the <b>DeviceObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> method.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</b> function initializes the <b>Size</b>, <b>Type</b>, and <b>TargetDeviceObject</b> members of the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

Typically, a driver sets the <b>TargetFileObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure after the driver has called <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</b>.

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example creates an I/O target object and opens the target by specifying a DEVICE_OBJECT structure. The sample driver obtains the DEVICE_OBJECT structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetdeviceproperty">NdisMGetDeviceProperty</a> (not shown).

```cpp
WDF_IO_TARGET_OPEN_PARAMS  openParams;
NTSTATUS  ntStatus;

ntStatus = WdfIoTargetCreate(
                             Adapter->WdfDevice,
                             WDF_NO_OBJECT_ATTRIBUTES,
                             &Adapter->IoTarget
                             );
if (!NT_SUCCESS(ntStatus)) {
    DEBUGP(MP_ERROR, ("WdfIoTargetCreate failed 0x%x\n", ntStatus));
    break;
}

WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE(
                                               &openParams,
                                               Adapter->NextDeviceObject
                                               );

ntStatus = WdfIoTargetOpen(Adapter->IoTarget,
                           &openParams);
if (!NT_SUCCESS(ntStatus)) {
    DEBUGP(MP_ERROR, ("WdfIoTargetOpen failed 0x%x\n", ntStatus));
    break;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_create_by_name">WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_open_by_name">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>

