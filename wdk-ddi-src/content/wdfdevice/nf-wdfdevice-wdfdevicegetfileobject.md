---
UID: NF:wdfdevice.WdfDeviceGetFileObject
title: WdfDeviceGetFileObject function (wdfdevice.h)
description: The WdfDeviceGetFileObject method returns a handle to the framework file object that is associated with a specified WDM file object.
old-location: wdf\wdfdevicegetfileobject.htm
tech.root: wdf
ms.assetid: 2e56d444-4248-4f00-b712-cbb3a4869302
ms.date: 02/26/2018
keywords: ["WdfDeviceGetFileObject function"]
ms.keywords: DFDeviceObjectGeneralRef_5aa48187-4a28-424c-9cd1-76cb5a33dc75.xml, WdfDeviceGetFileObject, WdfDeviceGetFileObject method, kmdf.wdfdevicegetfileobject, wdf.wdfdevicegetfileobject, wdfdevice/WdfDeviceGetFileObject
f1_keywords:
 - "wdfdevice/WdfDeviceGetFileObject"
 - "WdfDeviceGetFileObject"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceGetFileObject
targetos: Windows
req.typenames: 
---

# WdfDeviceGetFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceGetFileObject</b> method returns a handle to the framework file object that is associated with a specified WDM file object.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param FileObject [in]

A pointer to a WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure.


## -returns



<b>WdfDeviceGetFileObject</b> returns a handle to the framework file object that is associated with the specified WDM file object. If a framework file object was not created for the file, or if the <i>FileObject</i> pointer is invalid, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about framework file objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

The following code example obtains a pointer to a named WDM device object and its corresponding WDM file object, if the requested access to the objects can be granted. Then, the example obtains a handle to the framework file object that is associated with the WDM file object.

```cpp
PFILE_OBJECT  pWdmFileObject = NULL;
PDEVICE_OBJECT  pWdmDeviceObject = NULL;
WDFFILEOBJECT  fileObject = NULL;
NTSTATUS  status = STATUS_SUCCESS;
BOOLEAN  success = TRUE;

status = IoGetDeviceObjectPointer(
                                  &inputFileName,    // File name 
                                  FILE_ALL_ACCESS,   // Access mask
                                  &pWdmFileObject,   // Output pointer of WDM file object
                                  &pWdmDeviceObject  // Output pointer of WDM device object
                                  );

if(!NT_SUCCESS(status)){
    success = FALSE;
    break;
}

fileObject = WdfDeviceGetFileObject(
                                    gDeviceObject,  // Handle to device object
                                    pWdmFileObject  // Handle to WDM file object
                                    );
if(fileObject == NULL){
    success = FALSE;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>
 

 

