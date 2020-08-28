---
UID: NC:wdfdevice.EVT_WDF_DEVICE_FILE_CREATE
title: EVT_WDF_DEVICE_FILE_CREATE (wdfdevice.h)
description: A driver's EvtDeviceFileCreate callback function handles operations that must be performed when an application requests access to a device.
old-location: wdf\evtdevicefilecreate.htm
tech.root: wdf
ms.assetid: ee44c0bf-1fca-442d-8871-df6079e89ced
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_FILE_CREATE callback function"]
ms.keywords: DFDeviceObjectGeneralRef_74ee41b0-ed8c-4028-8f82-d747a4d916bb.xml, EVT_WDF_DEVICE_FILE_CREATE, EVT_WDF_DEVICE_FILE_CREATE callback, EvtDeviceFileCreate, EvtDeviceFileCreate callback function, kmdf.evtdevicefilecreate, wdf.evtdevicefilecreate, wdfdevice/EvtDeviceFileCreate
req.header: wdfdevice.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_FILE_CREATE
 - wdfdevice/EVT_WDF_DEVICE_FILE_CREATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceFileCreate
---

# EVT_WDF_DEVICE_FILE_CREATE callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceFileCreate</i> callback function handles operations that must be performed when an application requests access to a device.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Request 

[in]
A handle to a framework request object that represents a file creation request.

### -param FileObject 

[in]
A handle to a framework file object that describes a file that is being opened for the specified request. This parameter is <b>NULL</b> if the driver has specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WdfFileObjectNotRequired</a> for the <b>FileObjectClass </b>member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a> structure.

## -remarks

The framework calls a driver's <i>EvtDeviceFileCreate</i> callback function when a user application or another driver opens the device to perform an I/O operation, such as reading or writing a file. 

The driver can pass the <i>Request</i> handle to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a> to retrieve parameters that are associated with the file creation request. The parameters are stored in the <b>Parameters.Create</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure. 

This callback function is called synchronously, in the context of the thread that opens the device. 

To register an <i>EvtDeviceFileCreate</i> callback function, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

The driver must either complete the request or send it with [**WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags).

Alternatively, the driver can receive create requests in a queue. For more info, see [**WdfDeviceConfigureRequestDispatching**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching).

For more information about framework file objects and the <i>EvtDeviceFileCreate</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>

