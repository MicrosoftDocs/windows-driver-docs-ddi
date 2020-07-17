---
UID: NF:winsplp.RemovePrintDeviceObject
title: RemovePrintDeviceObject function (winsplp.h)
description: The RemovePrintDeviceObject function removes a device object from a print provider queue.
old-location: print\removeprintdeviceobject.htm
tech.root: print
ms.assetid: D94A669E-4293-4235-8BC4-C7883BB0C83C
ms.date: 04/20/2018
keywords: ["RemovePrintDeviceObject function"]
ms.keywords: RemovePrintDeviceObject, RemovePrintDeviceObject function [Print Devices], print.removeprintdeviceobject, winsplp/RemovePrintDeviceObject
f1_keywords:
 - "winsplp/RemovePrintDeviceObject"
 - "RemovePrintDeviceObject"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- WinSpool.drv
api_name:
- RemovePrintDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# RemovePrintDeviceObject function


## -description


<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>The <b>RemovePrintDeviceObject</b> function removes a device object from a print provider queue.


## -parameters




### -param hDeviceObject [in]

The HANDLE to the device object to be removed. This should be a device object that was  created with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-addprintdeviceobject">AddPrintDeviceObject</a>.


## -returns



The <b>RemovePrintDeviceObject</b> function returns S_OK, if the device object was removed successfully. Otherwise it returns an error. 

For example, this function can return HRESULT_FROM_WIN32(ERROR_INVALID_HANDLE), if an invalid device object handle was used to call the function. And note that, regardless of the return value, the device object HANDLE becomes invalid after a call to <b>RemovePrintDeviceObject</b> has completed.




## -remarks



Call <b>RemovePrintDeviceObject</b> to remove the device object for a printer that has been deleted. When the spooler services stops, all the device objects are automatically deleted, so it is not required to call <b>RemovePrintDeviceObject</b> for each printer device object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-addprintdeviceobject">AddPrintDeviceObject</a>
 

 

