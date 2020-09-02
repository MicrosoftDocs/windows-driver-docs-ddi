---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function (wdfiotarget.h)
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can open an I/O target by specifying the name of the device, file, or device interface.
old-location: wdf\wdf_io_target_open_params_init_create_by_name.htm
tech.root: wdf
ms.assetid: f6a6726a-83bc-4102-a6b6-74115ca4b889
ms.date: 02/26/2018
keywords: ["WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function"]
ms.keywords: DFIOTargetRef_5ae50d6e-6e3b-484a-afe9-6198860180b7.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME, WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function, kmdf.wdf_io_target_open_params_init_create_by_name, wdf.wdf_io_target_open_params_init_create_by_name, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
 - WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
 - wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfiotarget.h
api_name:
 - WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can open an I/O target by specifying the name of the device, file, or device interface. If the supplied name does not exist, the operating system will try to create it.

## -parameters

### -param Params 

[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.

### -param TargetDeviceName 

[in]
A value for the <b>TargetDeviceName</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

### -param DesiredAccess 

[in]
A value for the <b>DesiredAccess</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

## -remarks

If <i>TargetDeviceName</i> specifies the name of a file that already exists, the system replaces the existing file. If the file does not exist, the system creates it.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> method.


<b>KMDF </b>The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</b> function initializes the <b>Size</b>, <b>Type</b>, <b>TargetDeviceName</b>, <b>DesiredAccess</b>, and <b>CreateOptions</b> members of the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure.




<b>UMDF </b>The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</b> function initializes the <b>Size</b>, <b>Type</b>, <b>DesiredAccess</b>, and <b>TargetDeviceName</b>  members of the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure. It sets the <b>ShareAccess</b> member to zero. It also sets the <b>FileAttributes</b> member to <b>FILE_ATTRIBUTE_NORMAL</b>.



For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example creates an I/O target object and opens a target by specifying a file name.

```cpp
UNICODE_STRING  fileName;

RtlInitUnicodeString(
                     &fileName, 
                     (PCWSTR)PROTOCOL_INTERFACE_NAME
                     );

status = WdfIoTargetCreate(
                           Adapter->WdfDevice,
                           WDF_NO_OBJECT_ATTRIBUTES,
                           &Adapter->IoTarget
                           );
if (!NT_SUCCESS(status)) {
    DEBUGP(MP_ERROR, ("WdfIoTargetCreate failed 0x%x\n", status));
    return status;
}

WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME(
                                              &openParams,
                                              &fileName,
                                              STANDARD_RIGHTS_ALL
                                              );

status = WdfIoTargetOpen(
                         Adapter->IoTarget,
                         &openParams
                         );
if (!NT_SUCCESS(status)) {
    DEBUGP(MP_ERROR, ("WdfIoTargetOpen failed 0x%x\n", status));
    return status;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_existing_device">WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_open_by_name">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>

