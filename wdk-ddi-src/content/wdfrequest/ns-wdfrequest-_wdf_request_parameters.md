---
UID: NS:wdfrequest._WDF_REQUEST_PARAMETERS
title: _WDF_REQUEST_PARAMETERS (wdfrequest.h)
description: The WDF_REQUEST_PARAMETERS structure receives parameters that are associated with an I/O request.
old-location: wdf\wdf_request_parameters.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_PARAMETERS structure"]
ms.keywords: "*PWDF_REQUEST_PARAMETERS, DFRequestObjectRef_b3f1759e-7bdd-4222-8aea-502bd45e16bf.xml, PWDF_REQUEST_PARAMETERS, PWDF_REQUEST_PARAMETERS structure pointer, WDF_REQUEST_PARAMETERS, WDF_REQUEST_PARAMETERS structure, _WDF_REQUEST_PARAMETERS, kmdf.wdf_request_parameters, wdf.wdf_request_parameters, wdfrequest/PWDF_REQUEST_PARAMETERS, wdfrequest/WDF_REQUEST_PARAMETERS"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS
f1_keywords:
 - _WDF_REQUEST_PARAMETERS
 - wdfrequest/_WDF_REQUEST_PARAMETERS
 - PWDF_REQUEST_PARAMETERS
 - wdfrequest/PWDF_REQUEST_PARAMETERS
 - WDF_REQUEST_PARAMETERS
 - wdfrequest/WDF_REQUEST_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfrequest.h
api_name:
 - _WDF_REQUEST_PARAMETERS
 - PWDF_REQUEST_PARAMETERS
 - WDF_REQUEST_PARAMETERS
---

# _WDF_REQUEST_PARAMETERS structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_PARAMETERS</b> structure receives parameters that are associated with an I/O request.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field MinorFunction

The IRP minor function code, if any, that is associated with the I/O request. Some major function codes have associated minor function codes.

### -field Type

A <a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>-typed value that identifies the I/O request's type.

### -field Parameters

Parameters that are unique for each IRP major function code. This member contains a subset of the Parameters member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure.

### -field Parameters.Create

Parameters for <a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>.

### -field Parameters.Create.SecurityContext

### -field Parameters.Create.Options

### -field Parameters.Create.FileAttributes

### -field Parameters.Create.ShareAccess

### -field Parameters.Create.EaLength

### -field Parameters.Read

Parameters for <a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>.

### -field Parameters.Read.Length

### -field Parameters.Read.Key

### -field Parameters.Read.DeviceOffset

### -field Parameters.Write

Parameters for <a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>.

### -field Parameters.Write.Length

### -field Parameters.Write.Key

### -field Parameters.Write.DeviceOffset

### -field Parameters.DeviceIoControl

Parameters for <a href="/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a> and <a href="/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>.

### -field Parameters.DeviceIoControl.OutputBufferLength

### -field Parameters.DeviceIoControl.InputBufferLength

### -field Parameters.DeviceIoControl.IoControlCode

### -field Parameters.DeviceIoControl.Type3InputBuffer

### -field Parameters.Others

Use of this member is defined by the driver stack.

### -field Parameters.Others.Arg1

### -field Parameters.Others.Arg2

### -field Parameters.Others.IoControlCode

### -field Parameters.Others.Arg4

## -remarks

The <b>WDF_REQUEST_PARAMETERS</b> structure is used as input to <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>. Drivers must call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_parameters_init">WDF_REQUEST_PARAMETERS_INIT</a> to initialize this structure before they call <b>WdfRequestGetParameters</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_parameters_init">WDF_REQUEST_PARAMETERS_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>

