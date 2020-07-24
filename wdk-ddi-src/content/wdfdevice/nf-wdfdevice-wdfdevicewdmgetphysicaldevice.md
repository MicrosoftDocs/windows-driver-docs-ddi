---
UID: NF:wdfdevice.WdfDeviceWdmGetPhysicalDevice
title: WdfDeviceWdmGetPhysicalDevice function (wdfdevice.h)
description: The WdfDeviceWdmGetPhysicalDevice method retrieves the physical device's WDM PDO from the device stack.
old-location: wdf\wdfdevicewdmgetphysicaldevice.htm
tech.root: wdf
ms.assetid: 88bd9cc7-6769-4fdf-b149-2193d765fc6c
ms.date: 02/26/2018
keywords: ["WdfDeviceWdmGetPhysicalDevice function"]
ms.keywords: DFDeviceObjectGeneralRef_07f321bf-b857-4b36-81c0-452dc8acfc9a.xml, WdfDeviceWdmGetPhysicalDevice, WdfDeviceWdmGetPhysicalDevice method, kmdf.wdfdevicewdmgetphysicaldevice, wdf.wdfdevicewdmgetphysicaldevice, wdfdevice/WdfDeviceWdmGetPhysicalDevice
f1_keywords:
 - "wdfdevice/WdfDeviceWdmGetPhysicalDevice"
 - "WdfDeviceWdmGetPhysicalDevice"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceWdmGetPhysicalDevice
targetos: Windows
req.typenames: 
---

# WdfDeviceWdmGetPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceWdmGetPhysicalDevice</b> method retrieves the physical device's WDM PDO from the device stack.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



<b>WdfDeviceWdmGetPhysicalDevice</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.

<b>WdfDeviceWdmGetPhysicalDevice</b> returns <b>NULL</b> if the caller supplies a control device object.


## -remarks



The pointer that the <b>WdfDeviceWdmGetPhysicalDevice</b> method returns is valid until the framework device object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework device object, the pointer is valid until the callback function returns.


#### Examples

For a code example that uses <b>WdfDeviceWdmGetPhysicalDevice</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetattacheddevice">WdfDeviceWdmGetAttachedDevice</a>.

<div class="code"></div>


