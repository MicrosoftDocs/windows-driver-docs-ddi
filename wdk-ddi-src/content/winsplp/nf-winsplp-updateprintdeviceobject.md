---
UID: NF:winsplp.UpdatePrintDeviceObject
title: UpdatePrintDeviceObject function (winsplp.h)
description: The UpdatePrintDeviceObject function updates the properties of a device object that is in the print provider queue.
tech.root: print
ms.date: 11/30/2022
keywords: ["UpdatePrintDeviceObject function"]
ms.keywords: UpdatePrintDeviceObject, UpdatePrintDeviceObject function [Print Devices], print.updateprintdeviceobject, winsplp/UpdatePrintDeviceObject
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
 - UpdatePrintDeviceObject
 - winsplp/UpdatePrintDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WinSpool.drv
api_name:
 - UpdatePrintDeviceObject
---

## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

The **UpdatePrintDeviceObject** function updates the properties of a device object that is in the print provider queue.

## -parameters

### -param hPrinter [in]

The HANDLE to an open printer. This should be a handle that was returned by the **AddPrinter** or **OpenPrinter** spooler functions.

### -param hDeviceObject [in]

The HANDLE to the device object to be updated. This should be a device object that was created with [AddPrintDeviceObject](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-addprintdeviceobject).

## -returns

The **UpdatePrintDeviceObject** function returns S_OK, if the properties of the  device object were updated successfully. Otherwise it returns an error.

For example, this function can return HRESULT_FROM_WIN32(ERROR_INVALID_HANDLE), if the function call was made with an invalid HANDLE, or the device object was removed before the function call was made.

## -remarks

The [**PRINTER_INFO_2**](/windows/win32/printdocs/printer-info-2) structure is a good example of the kind of properties that **UpdatePrintDeviceObject** can update.

## -see-also

[AddPrintDeviceObject](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-addprintdeviceobject)

[**PRINTER_INFO_2**](/windows/win32/printdocs/printer-info-2)
