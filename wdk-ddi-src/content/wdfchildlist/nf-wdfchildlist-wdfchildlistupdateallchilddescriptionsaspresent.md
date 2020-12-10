---
UID: NF:wdfchildlist.WdfChildListUpdateAllChildDescriptionsAsPresent
title: WdfChildListUpdateAllChildDescriptionsAsPresent function (wdfchildlist.h)
description: The WdfChildListUpdateAllChildDescriptionsAsPresent method informs the framework that all of the child devices in a specified child list are plugged in and available.
old-location: wdf\wdfchildlistupdateallchilddescriptionsaspresent.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfChildListUpdateAllChildDescriptionsAsPresent function"]
ms.keywords: DFDeviceObjectChildListRef_55956590-2843-4486-acfb-0e85c01702a0.xml, WdfChildListUpdateAllChildDescriptionsAsPresent, WdfChildListUpdateAllChildDescriptionsAsPresent method, kmdf.wdfchildlistupdateallchilddescriptionsaspresent, wdf.wdfchildlistupdateallchilddescriptionsaspresent, wdfchildlist/WdfChildListUpdateAllChildDescriptionsAsPresent
req.header: wdfchildlist.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfChildListUpdateAllChildDescriptionsAsPresent
 - wdfchildlist/WdfChildListUpdateAllChildDescriptionsAsPresent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfChildListUpdateAllChildDescriptionsAsPresent
---

# WdfChildListUpdateAllChildDescriptionsAsPresent function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method informs the framework that all of the child devices in a specified child list are plugged in and available.

## -parameters

### -param ChildList 

[in]
A handle to a child list object.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <b>WdfChildListUpdateAllChildDescriptionsAsPresent</b> method is available in version 1.0 and later versions of KMDF.

For more information about child lists, see <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example informs the framework that all of the devices that a device list represents are plugged in and available.

```cpp
WdfChildListUpdateAllChildDescriptionsAsPresent(DeviceList);
```
