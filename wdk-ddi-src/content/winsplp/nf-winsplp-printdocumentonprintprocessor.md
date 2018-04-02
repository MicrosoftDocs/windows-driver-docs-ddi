---
UID: NF:winsplp.PrintDocumentOnPrintProcessor
title: PrintDocumentOnPrintProcessor function
author: windows-driver-content
description: A print processor's PrintDocumentOnPrintProcessor function converts a print job from a spooled format into raw data that can be sent to a print monitor.
old-location: print\printdocumentonprintprocessor.htm
old-project: print
ms.assetid: 1360a699-e312-40be-bf2f-b73b1419cfc5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PrintDocumentOnPrintProcessor, PrintDocumentOnPrintProcessor function [Print Devices], print.printdocumentonprintprocessor, spoolfnc_38f81d3c-62d9-4804-ad89-120c9a333a09.xml, winsplp/PrintDocumentOnPrintProcessor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: Nwprint.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Nwprint.lib
-	Nwprint.dll
api_name:
-	PrintDocumentOnPrintProcessor
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# PrintDocumentOnPrintProcessor function


## -description


A print processor's <code>PrintDocumentOnPrintProcessor</code> function converts a print job from a spooled format into raw data that can be sent to a print monitor.


## -parameters




### -param hPrintProcessor [in]

Caller-supplied print processor handle. This is the handle returned by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff559604">OpenPrintProcessor</a>.


### -param pDocumentName [in]

Caller-supplied pointer to the document name.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. If the operation fails, the function should call <b>SetLastError</b> to set an error code, and then return <b>FALSE</b>.




## -remarks



Print processors are required to export a <code>PrintDocumentOnPrintProcessor</code> function. The spooler calls the function after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559604">OpenPrintProcessor</a>. The function's purpose is to read the contents of the file named by <i>pDocumentName</i>, convert (if necessary) the file's data to a data stream that can be read by printer hardware, and to send the data stream back to the spooler. The spooler can then send the data stream to the appropriate <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">print monitor</a>.

If the input format is NT-based operating system EMF, the <code>PrintDocumentOnPrintProcessor</code> function can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549548">GDI functions for print processors</a>. For more information, see <a href="https://msdn.microsoft.com/c5e291d9-069c-4877-a167-862ba5794368">Processing a Print Job</a>.

The converted data stream must be sent back to the spooler by calling <b>WritePrinter</b>, which is described in the Microsoft Windows SDK documentation. For more information, see <a href="https://msdn.microsoft.com/c5e291d9-069c-4877-a167-862ba5794368">Processing a Print Job</a>.

The <code>PrintDocumentOnPrintProcessor</code> function must be written to handle requests to pause, resume, or cancel the print job. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546352">ControlPrintProcessor</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546352">ControlPrintProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559604">OpenPrintProcessor</a>
 

 

