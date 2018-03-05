---
UID: NF:winddiui.DrvPrinterEvent
title: DrvPrinterEvent function
author: windows-driver-content
description: A printer interface DLL's DrvPrinterEvent function is called by the print spooler when processing printer-specific events that might require action by the printer driver.
old-location: print\drvprinterevent.htm
old-project: print
ms.assetid: 7566f92d-0e25-44bf-a2b3-587bb11a7d03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvPrinterEvent, DrvPrinterEvent function [Print Devices], print.drvprinterevent, print_interface-graphics_5bfc5cb2-1835-4659-afa7-7b3bbb7ee051.xml, winddiui/DrvPrinterEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winddiui.h
api_name:
-	DrvPrinterEvent
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvPrinterEvent function


## -description


A printer interface DLL's <b>DrvPrinterEvent</b> function is called by the print spooler when processing printer-specific events that might require action by the printer driver.


## -syntax


````
BOOL DrvPrinterEvent(
  _In_ LPWSTR pPrinterName,
       int    DriverEvent,
       DWORD  Flags,
       LPARAM lParam
);
````


## -parameters




### -param pPrinterName [in]

Caller-supplied pointer to a NULL-terminated printer name string. The string format can be \\<i>Machine</i>\<i>PrinterName</i> to specify a remote printer, or <i>PrinterName</i> to specify a local printer.


### -param DriverEvent

Caller-supplied event code identifying the event. The following event codes are defined:

<table>
<tr>
<th>Event Code</th>
<th>Definition</th>
</tr>
<tr>
<td>
PRINTER_EVENT_ADD_CONNECTION

</td>
<td>
The spooler has just finished processing a call to its <b>AddPrinterConnection</b> function (described in the Microsoft Windows SDK documentation), which allows a client user to connect to a previously created remote printer.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_ATTRIBUTES_CHANGED

</td>
<td>
The attribute bits for a printer have changed. In response to an application's call to the <b>SetPrinter</b> function (described in the Windows SDK documentation), the spooler calls the printer driver's <b>DrvPrinterEvent</b> function, passing the event code in the call. When this event code is used, the <i>lParam</i> parameter points to a <a href="..\winddiui\ns-winddiui-_printer_event_attributes_info.md">PRINTER_EVENT_ATTRIBUTES_INFO</a> structure that describes the old and the new attributes.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_CACHE_DELETE

</td>
<td>
The spooler is deleting the client's file cache.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_CACHE_REFRESH

</td>
<td>
The spooler is updating the client's cached files.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_CONFIGURATION_CHANGE

</td>
<td>
Reserved.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_CONFIGURATION_UPDATE

</td>
<td>
The printer configuration has changed. When this event code is used, the <i>lParam</i> parameter points to a Unicode string that contains a notification formatted according the Bidi Notification Schema.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_DELETE_CONNECTION

</td>
<td>
The spooler has just finished processing a call to its <b>DeletePrinterConnection</b> function (described in the Windows SDK documentation), which allows a client user to remove a printer connection.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_DELETE

</td>
<td>
The spooler has just finished processing a call to its <b>DeletePrinter</b> function (described in the Windows SDK documentation), which allows an administrator to delete a printer instance.

</td>
</tr>
<tr>
<td>
PRINTER_EVENT_INITIALIZE

</td>
<td>
The spooler has just finished processing a call to its <b>AddPrinter</b> function, which allows an administrator to make a printer available on a server, or its <b>SetPrinter</b> function, which allows an administrator to modify a printer's state. <b>AddPrinter</b> and <b>SetPrinter</b> are described in the Windows SDK documentation.

In a client-side rendering connection, the client computer has just added the GUID printer.

The PRINTER_EVENT_INITIALIZE event specifies a <b>NULL</b> lParam parameter value for <b>DrvPrinterEvent</b> calls on Windows Vista and earlier releases. For Windows 7 and later releases, the lParam parameter is a user token handle. The print drivers may use the returned token handle to query user data or impersonate the user. 

</td>
</tr>
</table>
 


### -param Flags

Caller-supplied bit flag, defined as follows:

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
PRINTER_EVENT_FLAG_NO_UI

</td>
<td>
If set, the function <b>mustnot</b> display a user interface. During the installation of a print processor, print monitor, or printer driver, the only way in which a user interface is permitted is through the use of the <b>VendorSetup</b> directive. See <a href="https://msdn.microsoft.com/897072bb-e481-4c8d-a2bf-57b19c69ac0e">Printer INF File Entries</a> and <a href="https://msdn.microsoft.com/888125e9-a057-4e86-9df8-0086cedb368d">Customized Printer Setup Operations</a> for more information.

<div class="alert"><b>Important</b>  : Be aware that <b>VendorSetup</b> is now deprecated and should not be used by any <i>new</i> v3 or v4 drivers that you develop. This information about <b>VendorSetup</b> is provided for reference only, or for the maintenance of existing v3 drivers that already use this INF directive.</div>
<div> </div>
</td>
</tr>
</table>
 


### -param lParam

Not used unless the <i>DriverEvent</i> parameter is set to PRINTER_EVENT_ATTRIBUTES_CHANGED. In this case, <i>lParam</i> contains the address of a PRINTER_EVENT_ATTRIBUTES_INFO structure. (See the preceding description of the <i>DriverEvent</i> parameter.) For all other values of the <i>DriverEvent</i> parameter, the <i>lParam</i> parameter is <b>NULL</b>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>; otherwise, it should return <b>FALSE</b>. Currently, however, the only time the function's return value is checked is when the spooler has called <b>DrvPrinterEvent</b> during processing of the <b>AddPrinter</b> function, with <i>DriverEvent</i> set to PRINTER_EVENT_INITIALIZE. If <b>DrvPrinterEvent</b> returns <b>FALSE</b> in this case, the spooler does not create the printer and instead causes <b>AddPrinter</b> to fail.




## -remarks



All <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLLs</a> must provide a <b>DrvPrinterEvent</b> function, and the function must support the PRINTER_EVENT_INITIALIZE event code. Support for all other event codes is optional.

Registry settings stored when handling a PRINTER_EVENT_INITIALIZE event should be stored under the HKEY_LOCAL_MACHINE key by calling <b>SetPrinterData</b>. For the PRINTER_EVENT_INITIALIZE and PRINTER_EVENT_DELETE event codes, the spooler verifies that the caller has administrative privilege and calls <b>DrvPrinterEvent</b> while impersonating the caller.

In contrast, if you need to store settings in the registry when handling a PRINTER_EVENT_ADD_CONNECTION event, the printer interface DLL should write them under the HKEY_CURRENT_USER key so that they are stored on a per-user basis. Then if a user with a roaming profile logs onto another system, the connection follows the user. The <b>DrvPrinterEvent</b> function is called only when the user first makes the connection, and not when the user subsequently logs onto other systems using the roaming profile.

For the PRINTER_EVENT_ADD_CONNECTION and PRINTER_EVENT_DELETE_CONNECTION event codes, the <b>DrvPrinterEvent</b> function's execution context is the calling application (usually the Print Folder), and the function can display a user interface. For all other event codes, the execution context is the print spooler and a user interface cannot be displayed.

An example of a driver that might display a user interface when a connection is made is a FAX driver, which could prompt the user for the name and telephone number of the user (FAX sender), and save the information until the connection is deleted.

An example of the type of file that might be stored in a client cache is a large font-metrics file that contains too much information to be written to the registry. When the <b>DrvPrinterEvent</b> function's event code is PRINTER_EVENT_CACHE_REFRESH, the printer interface DLL can reload the file from the server to ensure the cache is up to date.



