---
UID: NS:winsplp._PRINTPROCESSOROPENDATA
title: _PRINTPROCESSOROPENDATA (winsplp.h)
description: The PRINTPROCESSOROPENDATA structure is used as an input parameter to a print processor's OpenPrintProcessor function.
old-location: print\printprocessoropendata.htm
tech.root: print
ms.assetid: d7160747-d81c-407a-bbf0-7ec5b3210c13
ms.date: 04/20/2018
keywords: ["_PRINTPROCESSOROPENDATA structure"]
ms.keywords: "*LPPRINTPROCESSOROPENDATA, *PPRINTPROCESSOROPENDATA, LPPRINTPROCESSOROPENDATA, LPPRINTPROCESSOROPENDATA structure pointer [Print Devices], PPRINTPROCESSOROPENDATA, PPRINTPROCESSOROPENDATA structure pointer [Print Devices], PRINTPROCESSOROPENDATA, PRINTPROCESSOROPENDATA structure [Print Devices], _PRINTPROCESSOROPENDATA, print.printprocessoropendata, spoolfnc_d24c3eae-da3e-473a-bd25-5ec09d23fe89.xml, winsplp/LPPRINTPROCESSOROPENDATA, winsplp/PPRINTPROCESSOROPENDATA, winsplp/PRINTPROCESSOROPENDATA"
f1_keywords:
 - "winsplp/PRINTPROCESSOROPENDATA"
 - "PRINTPROCESSOROPENDATA"
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsplp.h
api_name:
- PRINTPROCESSOROPENDATA
targetos: Windows
req.typenames: PRINTPROCESSOROPENDATA, *PPRINTPROCESSOROPENDATA, *LPPRINTPROCESSOROPENDATA
---

# _PRINTPROCESSOROPENDATA structure


## -description


The PRINTPROCESSOROPENDATA structure is used as an input parameter to a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a> function.


## -struct-fields




### -field pDevMode

Spooler-supplied pointer to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure.


### -field pDatatype

Spooler-supplied pointer to a string representing the print job's data type.


### -field pParameters

Spooler-supplied pointer to a parameter string, as specified in a JOB_INFO_2 structure supplied to a call to the <b>SetJob</b> function, described in the Microsoft Windows SDK documentation.


### -field pDocumentName

Spooler-supplied pointer to a string representing the name of the input document associated with the print job. 


### -field JobId

Spooler-supplied value identifying the print job.


### -field pOutputFile

Spooler-supplied pointer to a string representing the name of the output spool file.


### -field pPrinterName

Spooler-supplied pointer to a string representing the name of the printer to be used.


## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a>
 

 

