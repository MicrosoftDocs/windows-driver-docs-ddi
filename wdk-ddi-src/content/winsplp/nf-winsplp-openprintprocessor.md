---
UID: NF:winsplp.OpenPrintProcessor
title: OpenPrintProcessor function
author: windows-driver-content
description: A print processor's OpenPrintProcessor function prepares the print processor for printing a job and returns a handle.
old-location: print\openprintprocessor.htm
old-project: print
ms.assetid: bab79fb6-1bb0-48ec-9d60-fcb6e679b758
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OpenPrintProcessor, OpenPrintProcessor function [Print Devices], print.openprintprocessor, spoolfnc_b8a185f0-4289-49bb-bb98-b6f54b66fa70.xml, winsplp/OpenPrintProcessor
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
-	OpenPrintProcessor
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# OpenPrintProcessor function


## -description


A print processor's <code>OpenPrintProcessor</code> function prepares the print processor for printing a job and returns a handle.


## -syntax


````
HANDLE OpenPrintProcessor(
  _In_ LPWSTR                  pPrinterName,
  _In_ PPRINTPROCESSOROPENDATA pPrintProcessorOpenData
);
````


## -parameters




### -param pPrinterName [in]

Caller-supplied pointer to the name of the printer for which the print processor is being opened.


### -param pPrintProcessorOpenData [in]

Caller-supplied pointer to a <a href="..\winsplp\ns-winsplp-_printprocessoropendata.md">PRINTPROCESSOROPENDATA</a> structure.


## -returns



If the operation succeeds, the function should return a handle that can be used as an input argument for subsequent calls to <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a>, <a href="..\winsplp\nf-winsplp-controlprintprocessor.md">ControlPrintProcessor</a>, and <a href="..\winsplp\nf-winsplp-closeprintprocessor.md">ClosePrintProcessor</a>. If the operation fails, the function should call <b>SetLastError</b> to set an error code, and then return <b>NULL</b>.




## -remarks



Print processors are required to export an <code>OpenPrintProcessor</code> function. The spooler calls the function when a print job is available. The function should perform initialization operations that are required before a job can be processed, based on the job's data type.

The function must return a handle. Typically, the handle is a pointer to an internal structure. The structure must contain a pointer to the printer's name and a pointer to the printer's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure, both of which are received in the <a href="..\winsplp\ns-winsplp-_printprocessoropendata.md">PRINTPROCESSOROPENDATA</a> structure. These two pointers are required by the print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function, and this latter function receives the handle as input when the spooler calls it.




## -see-also

<a href="..\winsplp\nf-winsplp-closeprintprocessor.md">ClosePrintProcessor</a>



<a href="..\winsplp\nf-winsplp-controlprintprocessor.md">ControlPrintProcessor</a>



<a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a>



<a href="..\winsplp\ns-winsplp-_printprocessoropendata.md">PRINTPROCESSOROPENDATA</a>



 

 


