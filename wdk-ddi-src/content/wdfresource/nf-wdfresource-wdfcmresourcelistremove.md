---
UID: NF:wdfresource.WdfCmResourceListRemove
title: WdfCmResourceListRemove function (wdfresource.h)
description: The WdfCmResourceListRemove method removes a resource descriptor from a specified resource list.
old-location: wdf\wdfcmresourcelistremove.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfCmResourceListRemove function"]
ms.keywords: DFResourceObjectRef_5b1c7fce-45d2-454e-9d21-3f8d460ba99f.xml, WdfCmResourceListRemove, WdfCmResourceListRemove method, kmdf.wdfcmresourcelistremove, wdf.wdfcmresourcelistremove, wdfresource/WdfCmResourceListRemove
req.header: wdfresource.h
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfCmResourceListRemove
 - wdfresource/WdfCmResourceListRemove
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfCmResourceListRemove
---

# WdfCmResourceListRemove function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCmResourceListRemove</b> method removes a resource descriptor from a specified resource list.

## -parameters

### -param List [in]


A handle to a framework resource-list object that represents a list of hardware resources for a device.

### -param Index [in]


A zero-based value that is used as an index into the resource list that <i>List</i> specifies.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <b>WdfCmResourceListRemove</b> method removes the resource descriptor that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfCmResourceListRemove</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource lists, see <a href="/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example removes the third resource descriptor from the raw and translated lists of hardware resources that an <a href="/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_remove_added_resources">EvtDeviceRemoveAddedResources</a> callback function receives.

```cpp
NTSTATUS
MyEvtDeviceRemoveAddedResources(
    WDFDEVICE Device,
    WDFCMRESLIST ResourcesRaw,
    WDFCMRESLIST ResourcesTranslated
    )
{
...
    WdfCmResourceListRemove(
                            ResourcesRaw,
                            2
                            );
    WdfCmResourceListRemove(
                            ResourcesTranslated,
                            2
                            );
...

}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistremovebydescriptor">WdfCmResourceListRemoveByDescriptor</a>
