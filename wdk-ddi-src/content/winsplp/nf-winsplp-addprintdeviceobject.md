---
UID: NF:winsplp.AddPrintDeviceObject
title: AddPrintDeviceObject function (winsplp.h)
description: The AddPrintDeviceObject print provider function creates a device object for a print provider queue.
old-location: print\addprintdeviceobject.htm
tech.root: print
ms.assetid: C01071FD-7D1D-4D6F-AFDD-355FFDA699EA
ms.date: 04/20/2018
keywords: ["AddPrintDeviceObject function"]
ms.keywords: AddPrintDeviceObject, AddPrintDeviceObject function [Print Devices], print.addprintdeviceobject, winsplp/AddPrintDeviceObject
req.header: winsplp.h
req.include-header: Winspool.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WinSpool.lib
req.dll: WinSpool.drv
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AddPrintDeviceObject
 - winsplp/AddPrintDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WinSpool.drv
api_name:
 - AddPrintDeviceObject
---

# AddPrintDeviceObject function


## -description

<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>The <b>AddPrintDeviceObject</b> print provider function creates a device object for a print provider queue.

## -parameters

### -param hPrinter 

[in]
A HANDLE to an open printer. This should be a HANDLE returned by the <b>AddPrinter</b> or <b>OpenPrinter</b> spooler functions.

### -param phDeviceObject 

[out]
A HANDLE to the device object, if it was created successfully.

## -returns

The <b>AddPrintDeviceObject</b> function returns S_OK, if the device object was created successfully.
    Otherwise it returns an error.

## -remarks

The <b>AddPrintDeviceObject</b> function should be called in the following situations:

<b>User installs a Printer</b>

<ul>
<li>
The print provider should call this function after installing the printer.

</li>
<li>
The function must be called by impersonating the user who is installing the printer.

</li>
</ul>
<b>Print Provider is intialized after spooler service starts</b>

<ul>
<li>
The print provider should call this function for each previously-installed Printer owned by the provider. During this time, <b>AddPrintDeviceObject</b> doesn't have to impersonate the user context when it is called.<div class="alert"><b>Note</b>  Any device object that is added using  <b>AddPrintDeviceObject</b> will persist until you remove it using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-removeprintdeviceobject">RemovePrintDeviceObject</a>, or 
    until the spooler service restarts. And when the spooler services stops, all the device objects are automatically deleted.</div>
<div> </div>


</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-removeprintdeviceobject">RemovePrintDeviceObject</a>

