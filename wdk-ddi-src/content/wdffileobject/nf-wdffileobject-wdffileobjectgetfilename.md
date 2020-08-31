---
UID: NF:wdffileobject.WdfFileObjectGetFileName
title: WdfFileObjectGetFileName function (wdffileobject.h)
description: The WdfFileObjectGetFileName method returns the file name that a specified framework file object contains.
old-location: wdf\wdffileobjectgetfilename.htm
tech.root: wdf
ms.assetid: 9d4e45c7-ed1f-476a-8522-4213ac42a3c3
ms.date: 02/26/2018
keywords: ["WdfFileObjectGetFileName function"]
ms.keywords: DFFileObjectRef_07be4c38-fa04-41d3-8f8e-f7ec5ed6ff18.xml, WdfFileObjectGetFileName, WdfFileObjectGetFileName method, kmdf.wdffileobjectgetfilename, wdf.wdffileobjectgetfilename, wdffileobject/WdfFileObjectGetFileName
req.header: wdffileobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfFileObjectGetFileName
 - wdffileobject/WdfFileObjectGetFileName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfFileObjectGetFileName
---

# WdfFileObjectGetFileName function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFileObjectGetFileName</b> method returns the file name that a specified framework file object contains.

## -parameters

### -param FileObject 

[in]
A handle to a framework file object.

## -returns

<b>WdfFileObjectGetFileName</b> returns a pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the file name. The method returns <b>NULL</b> if there is no WDM file object for the specified framework file object, or if it is called at an IRQL higher than PASSIVE_LEVEL.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If a driver specified a reference string when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatedeviceinterface">WdfDeviceCreateDeviceInterface</a>, <b>WdfFileObjectGetFileName</b> returns the reference string prepended by a backslash. To determine the reference string, remove the backslash.

The returned string can contain a file name or a reference string. The string does not contain the device name. If an application or kernel-mode component has opened the device instead of a file, with no reference string, the <b>Length</b> member of the returned UNICODE_STRING structure is zero.

Your driver should only call <b>WdfFileObjectGetFileName</b> while it is processing a file creation request (<b>WdfRequestTypeCreate</b> request type). Your driver might process <b>WdfRequestTypeCreate</b>-typed I/O requests in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function.

Or, instead of providing an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a> to set an I/O queue to receive all file creation requests (<b>WdfRequestTypeCreate</b> request type). The driver will subsequently receive file creation requests in the queue's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a> request handler.

 For more information about framework file objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.

For more information about file names, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/controlling-device-namespace-access">Controlling Device Namespace Access</a>.

For more information about reference strings, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function can obtain the name of the file that an application has opened.

```cpp
VOID
MyEvtDeviceFileCreate (
    IN WDFDEVICE  Device,
    IN WDFREQUEST  Request,
    IN WDFFILEOBJECT  FileObject
    )
{
    PUNICODE_STRING  fileName;

    fileName = WdfFileObjectGetFileName(FileObject);
...

}
```

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatedeviceinterface">WdfDeviceCreateDeviceInterface</a>

