---
UID: NF:wdffileobject.WdfFileObjectGetDevice
title: WdfFileObjectGetDevice function (wdffileobject.h)
description: The WdfFileObjectGetDevice method returns the framework device object that is associated with a specified framework file object.
old-location: wdf\wdffileobjectgetdevice.htm
tech.root: wdf
ms.assetid: 10bb8bbd-0347-4ceb-844e-87f049813684
ms.date: 02/26/2018
keywords: ["WdfFileObjectGetDevice function"]
ms.keywords: DFFileObjectRef_4986a619-be10-4eca-84dd-9ae1dcac423f.xml, WdfFileObjectGetDevice, WdfFileObjectGetDevice method, kmdf.wdffileobjectgetdevice, wdf.wdffileobjectgetdevice, wdffileobject/WdfFileObjectGetDevice
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfFileObjectGetDevice
 - wdffileobject/WdfFileObjectGetDevice
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
 - WdfFileObjectGetDevice
---

# WdfFileObjectGetDevice function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFileObjectGetDevice</b> method returns the framework device object that is associated with a specified framework file object.

## -parameters

### -param FileObject 

[in]
A handle to a framework file object.

## -returns

<b>WdfFileObjectGetDevice</b> returns a handle to the framework device object that is associated with the specified framework file object.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about framework file objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback function can obtain the framework device object that is associated with a specified framework file object.

```cpp
VOID
MyEvtFileClose(
    IN WDFFILEOBJECT  FileObject
    )
{
    WDFDEVICE device;

    device = WdfFileObjectGetDevice(FileObject);
...
}
```

