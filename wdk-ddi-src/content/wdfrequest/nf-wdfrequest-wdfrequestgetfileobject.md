---
UID: NF:wdfrequest.WdfRequestGetFileObject
title: WdfRequestGetFileObject function (wdfrequest.h)
description: The WdfRequestGetFileObject method retrieves the framework file object that is associated with a specified I/O request.
old-location: wdf\wdfrequestgetfileobject.htm
tech.root: wdf
ms.assetid: 0c5a1e12-b66f-4bcb-bb9d-739b883fe9c2
ms.date: 02/26/2018
keywords: ["WdfRequestGetFileObject function"]
ms.keywords: DFRequestObjectRef_cfa39375-4338-428c-aec5-52479b2a91ea.xml, WdfRequestGetFileObject, WdfRequestGetFileObject method, kmdf.wdfrequestgetfileobject, wdf.wdfrequestgetfileobject, wdfrequest/WdfRequestGetFileObject
f1_keywords:
 - "wdfrequest/WdfRequestGetFileObject"
 - "WdfRequestGetFileObject"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FileObjectConfigured, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
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
- WdfRequestGetFileObject
targetos: Windows
req.typenames: 
---

# WdfRequestGetFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetFileObject</b> method retrieves the framework file object that is associated with a specified I/O request.


## -parameters




### -param Request 
[in]
A handle to a framework request object.


## -returns



<b>WdfRequestGetFileObject</b> returns a handle to the framework file object, if the framework has created a file object for the specified request. Otherwise, this method returns <b>NULL</b>. (A driver typically tests for a <b>NULL</b> return value only if it sets the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WdfFileObjectCanBeOptional</a> bit flag in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a> structure.)

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfRequestGetFileObject</b> method returns <b>NULL</b> if either:

<ul>
<li>
Your driver has not called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> and specified a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WDF_FILEOBJECT_CLASS</a> value that causes the framework to create file objects.

</li>
<li>
Another driver sent a read, write, or I/O control request to your driver without first sending a request type of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WdfRequestTypeCreate</a>.

</li>
</ul>
For more information about <b>WdfRequestGetFileObject</b> and framework file objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

The following code example obtains an I/O request's file object and then calls a driver-defined routine that obtains a pointer to the file object's context space.

```cpp
VOID
MyEvtIoWrite(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    WDFFILEOBJECT  fileObject;
    PFILE_OPEN_CONTEXT  pOpenContext;

    fileObject = WdfRequestGetFileObject(Request);
    pOpenContext = GetFileObjectContext(fileObject)->OpenContext;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WDF_FILEOBJECT_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a>
 

 

