---
UID: NF:winddiui.DrvPrinterEvent
title: DrvPrinterEvent function (winddiui.h)
description: A printer interface DLL's DrvPrinterEvent function is called by the print spooler when processing printer-specific events that might require action by the printer driver.
tech.root: print
ms.date: 01/04/2023
keywords: ["DrvPrinterEvent function"]
ms.keywords: DrvPrinterEvent, DrvPrinterEvent function [Print Devices], print.drvprinterevent, print_interface-graphics_5bfc5cb2-1835-4659-afa7-7b3bbb7ee051.xml, winddiui/DrvPrinterEvent
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - DrvPrinterEvent
 - winddiui/DrvPrinterEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvPrinterEvent
---

## -description

A printer interface DLL's **DrvPrinterEvent** function is called by the print spooler when processing printer-specific events that might require action by the printer driver.

## -parameters

### -param pPrinterName [in]

Caller-supplied pointer to a NULL-terminated printer name string. The string format can be \\*Machine*\\*PrinterName* to specify a remote printer, or *PrinterName* to specify a local printer.

### -param DriverEvent

Caller-supplied event code identifying the event. The following event codes are defined:

| Event code | Definition |
|---|---|
| PRINTER_EVENT_ADD_CONNECTION | The spooler has just finished processing a call to its [**AddPrinterConnection**](/windows/win32/printdocs/addprinterconnection) function, which allows a client user to connect to a previously created remote printer. |
| PRINTER_EVENT_ATTRIBUTES_CHANGED | The attribute bits for a printer have changed. In response to an application's call to the [**SetPrinter**](/windows/win32/printdocs/setprinter) function, the spooler calls the printer driver's **DrvPrinterEvent** function, passing the event code in the call. When this event code is used, the *lParam* parameter points to a [PRINTER_EVENT_ATTRIBUTES_INFO](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_printer_event_attributes_info) structure that describes the old and the new attributes. |
| PRINTER_EVENT_CACHE_DELETE | The spooler is deleting the client's file cache. |
| PRINTER_EVENT_CACHE_REFRESH | The spooler is updating the client's cached files. |
| PRINTER_EVENT_CONFIGURATION_CHANGE | Reserved. |
| PRINTER_EVENT_CONFIGURATION_UPDATE | The printer configuration has changed. When this event code is used, the *lParam* parameter points to a Unicode string that contains a notification formatted according the Bidi Notification Schema. |
| PRINTER_EVENT_DELETE_CONNECTION | The spooler has just finished processing a call to its [**DeletePrinterConnection**](/windows/win32/printdocs/deleteprinterconnection) function, which allows a client user to remove a printer connection. |
| PRINTER_EVENT_DELETE | The spooler has just finished processing a call to its [**DeletePrinter**](/windows/win32/printdocs/deleteprinter) function, which allows an administrator to delete a printer instance. |
| PRINTER_EVENT_INITIALIZE | The spooler has just finished processing a call to its [**AddPrinter**](/windows/win32/printdocs/addprinter) function, which allows an administrator to make a printer available on a server, or its [**SetPrinter**](/windows/win32/printdocs/setprinter) function, which allows an administrator to modify a printer's state. In a client-side rendering connection, the client computer has just added the GUID printer. The PRINTER_EVENT_INITIALIZE event specifies a **NULL** lParam parameter value for **DrvPrinterEvent** calls on Windows Vista and earlier releases. For Windows 7 and later releases, the lParam parameter is a user token handle. The print drivers may use the returned token handle to query user data or impersonate the user. |

### -param Flags

Caller-supplied bit flag, defined as follows:

| Value | Definition |
|---|---|
| PRINTER_EVENT_FLAG_NO_UI | If set, the function **must not** display a user interface. During the installation of a print processor, print monitor, or printer driver, the only way in which a user interface is permitted is through the use of the **VendorSetup** directive. See [Printer INF File Entries](/windows-hardware/drivers/print/printer-inf-file-entries) and [Customized Printer Setup Operations](/windows-hardware/drivers/print/customized-printer-setup-operations) for more information. |

> [!CAUTION]
> The **VendorSetup** directive is deprecated and should not be used by any *new* v3 or v4 drivers that you develop. This information about **VendorSetup** is provided for reference only, or for the maintenance of existing v3 drivers that already use this INF directive.

### -param lParam

Not used unless the *DriverEvent* parameter is set to PRINTER_EVENT_ATTRIBUTES_CHANGED. In this case, *lParam* contains the address of a PRINTER_EVENT_ATTRIBUTES_INFO structure. (See the preceding description of the *DriverEvent* parameter.) For all other values of the *DriverEvent* parameter, the *lParam* parameter is **NULL**.

## -returns

If the operation succeeds, the function should return **TRUE**; otherwise, it should return **FALSE**. Currently, however, the only time the function's return value is checked is when the spooler has called **DrvPrinterEvent** during processing of the **AddPrinter** function, with *DriverEvent* set to PRINTER_EVENT_INITIALIZE. If **DrvPrinterEvent** returns **FALSE** in this case, the spooler does not create the printer and instead causes **AddPrinter** to fail.

## -remarks

All [printer interface DLLs](/windows-hardware/drivers/print/printer-interface-dll) must provide a **DrvPrinterEvent** function, and the function must support the PRINTER_EVENT_INITIALIZE event code. Support for all other event codes is optional.

Registry settings stored when handling a PRINTER_EVENT_INITIALIZE event should be stored under the HKEY_LOCAL_MACHINE key by calling **SetPrinterData**. For the PRINTER_EVENT_INITIALIZE and PRINTER_EVENT_DELETE event codes, the spooler verifies that the caller has administrative privilege and calls **DrvPrinterEvent** while impersonating the caller.

In contrast, if you need to store settings in the registry when handling a PRINTER_EVENT_ADD_CONNECTION event, the printer interface DLL should write them under the HKEY_CURRENT_USER key so that they are stored on a per-user basis. Then if a user with a roaming profile logs onto another system, the connection follows the user. The **DrvPrinterEvent** function is called only when the user first makes the connection, and not when the user subsequently logs onto other systems using the roaming profile.

For the PRINTER_EVENT_ADD_CONNECTION and PRINTER_EVENT_DELETE_CONNECTION event codes, the **DrvPrinterEvent** function's execution context is the calling application (usually the Print Folder), and the function can display a user interface. For all other event codes, the execution context is the print spooler and a user interface cannot be displayed.

An example of a driver that might display a user interface when a connection is made is a FAX driver, which could prompt the user for the name and telephone number of the user (FAX sender), and save the information until the connection is deleted.

An example of the type of file that might be stored in a client cache is a large font-metrics file that contains too much information to be written to the registry. When the **DrvPrinterEvent** function's event code is PRINTER_EVENT_CACHE_REFRESH, the printer interface DLL can reload the file from the server to ensure the cache is up to date.
