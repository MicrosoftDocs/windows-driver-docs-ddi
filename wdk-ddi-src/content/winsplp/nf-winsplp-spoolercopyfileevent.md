---
UID: NF:winsplp.SpoolerCopyFileEvent
title: SpoolerCopyFileEvent function (winsplp.h)
description: A Point and Print DLL's SpoolerCopyFileEvent function receives notifications of events associated with copying print queue-associated files to a print client, when the client connects to a print server.
old-location: print\spoolercopyfileevent.htm
tech.root: print
ms.assetid: 39e9b596-7726-439c-8ad9-a987fdfd3860
ms.date: 04/20/2018
ms.keywords: SpoolerCopyFileEvent, SpoolerCopyFileEvent function [Print Devices], poprfnc_e85f9707-18cf-4cd5-aece-ebcd5fd09270.xml, print.spoolercopyfileevent, winsplp/SpoolerCopyFileEvent
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Universal
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
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Mscms.dll
api_name:
- SpoolerCopyFileEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# SpoolerCopyFileEvent function


## -description


A Point and Print DLL's <code>SpoolerCopyFileEvent</code> function receives notifications of events associated with copying print queue-associated files to a print client, when the client connects to a print server.


## -parameters




### -param pszPrinterName [in]

Caller-supplied pointer to a string representing the printer name.


### -param pszKey [in]

Caller-supplied pointer to a string representing a subkey under the printer's <b>CopyFiles</b> registry key. This subkey identifies the component to which the Point and Print DLL belongs.


### -param dwCopyFileEvent [in]

Caller-supplied flag that identifies the event being reported. Valid flag values are contained in the following table.

<table>
<tr>
<th>Flag</th>
<th>When Received</th>
<th>Where Received</th>
</tr>
<tr>
<td>
COPYFILE_EVENT_ADD_PRINTER_CONNECTION

</td>
<td>
After a client application has called <b>AddPrinterConnection</b>.

</td>
<td>
Client copy of <code>SpoolerCopyFileEvent</code>. The calling context is the client application.

</td>
</tr>
<tr>
<td>
COPYFILE_EVENT_DELETE_PRINTER

</td>
<td>
After a call to <b>DeletePrinter</b> has been made.

</td>
<td>
Client copy of <code>SpoolerCopyFileEvent</code>. The calling context is the client's spooler.

</td>
</tr>
<tr>
<td>
COPYFILE_EVENT_DELETE_PRINTER_CONNECTION

</td>
<td>
After a client application has called <b>DeletePrinterConnection</b>.

</td>
<td>
Client copy of <code>SpoolerCopyFileEvent</code>. The calling context is the client application.

</td>
</tr>
<tr>
<td>
COPYFILE_EVENT_FILES_CHANGED

</td>
<td>
After the client has downloaded the files specified under the <b>pszKey</b> subkey of the printer's <b>CopyFiles</b> registry key.

</td>
<td>
Client copy of <code>SpoolerCopyFileEvent</code>. The calling context is the client's spooler.

</td>
</tr>
<tr>
<td>
COPYFILE_EVENT_SET_PRINTER_DATAEX

</td>
<td>
After a call to <b>SetPrinterDataEx</b> has been processed on the server.

</td>
<td>
Server copy of <code>SpoolerCopyFileEvent</code>. The calling context is the client application, by impersonation.

</td>
</tr>
</table>
 


## -returns



If the function encounters errors, the function should return <b>FALSE</b>. Otherwise, it should return <b>TRUE</b>.




## -remarks



All <a href="https://msdn.microsoft.com/7ead940e-8426-4756-890f-f3607dc1f9ca">Point and Print DLLs</a> must export a <code>SpoolerCopyFileEvent</code> function, which is called by the print spooler. Its purpose is to allow a Point and Print DLL to be notified of events related to the downloading of print queue-associated files, from a print server to a client system, when an application on the client connects to the server. For a complete description of the steps involved in creating a Point and Print connection, see <a href="https://msdn.microsoft.com/a41bed5e-a006-4b9e-aa71-d2bcd154fae2">Supporting Point and Print</a>.

A Point and Print DLL executes on both the server and the client. The <code>SpoolerCopyFileEvent</code> function can determine where it is executing by reading the contents of <i>dwCopyFileEvent</i>, which supplies a flag indicating the event. The function should process the event and return. If no processing is necessary, the function should just return <b>TRUE</b>.

If <i>dwCopyFileEvent</i> is COPYFILE_EVENT_ADD_PRINTER_CONNECTION or COPYFILE_EVENT_ADD_PRINTER_CONNECTION, the string supplied by <i>pszPrinterName</i> includes the server name.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549896">GenerateCopyFilePaths</a>
 

 

