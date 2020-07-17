---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function (wdfiotarget.h)
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can open an I/O target by specifying a filename.
old-location: wdf\wdf_io_target_open_params_init_open_by_file.htm
tech.root: wdf
ms.assetid: 6C8CA2A8-D39E-4524-A909-102D8310AC72
ms.date: 02/26/2018
keywords: ["WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function"]
ms.keywords: WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE, WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function, wdf.wdf_io_target_open_params_init_open_by_file, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE
f1_keywords:
 - "wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE"
 - "WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfiotarget.h
api_name:
- WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can open an I/O target by specifying a filename.


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


### -param FileName [in, optional]

A value for the <b>FileName</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure. Most drivers specify <b>NULL</b> here unless the lower target supports <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/controlling-device-namespace-access">Device Namespace Access</a>.


## -remarks



The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure and sets its <b>Size</b> member. It also sets the structure's <b>Type</b> member to <b>WdfIoTargetOpenLocalTargetByFile</b> and sets the <b>FileName</b> member if the driver supplies a filename.

A driver can explicitly close the I/O target by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose">WdfIoTargetClose</a>. If the driver does not explicitly close the target, the framework closes the target automatically when the device is removed (an I/O target is by default parented to the device).


#### Examples

The following code example shows how a UMDF driver can open a local target with a file object as described in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WDF_IO_TARGET_OPEN_TYPE</a>:

```cpp
WDF_OBJECT_ATTRIBUTES  ioTargetAttrib;
WDFIOTARGET  ioTarget;
WDF_IO_TARGET_OPEN_PARAMS  openParams;

//
// Create target
//
WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&ioTargetAttrib, TARGET_DEVICE_INFO);
status = WdfIoTargetCreate(device, &ioTargetAttrib, &ioTarget);
if (!NT_SUCCESS(status)) {
    return status;
}

//
// Open target
//
WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE(&openParams, NULL);
status = WdfIoTargetOpen(ioTarget, &openParams);
if (!NT_SUCCESS(status)) {
    WdfObjectDelete(ioTarget);
    return status;
}

//
// create a request
//


//
// Format the request for the above target
//


//
// Send request to above target
//

```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WDF_IO_TARGET_OPEN_TYPE</a>
 

 

