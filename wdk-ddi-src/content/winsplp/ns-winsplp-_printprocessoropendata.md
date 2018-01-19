---
UID: NS:winsplp._PRINTPROCESSOROPENDATA
title: _PRINTPROCESSOROPENDATA
author: windows-driver-content
description: The PRINTPROCESSOROPENDATA structure is used as an input parameter to a print processor's OpenPrintProcessor function.
old-location: print\printprocessoropendata.htm
old-project: print
ms.assetid: d7160747-d81c-407a-bbf0-7ec5b3210c13
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _PRINTPROCESSOROPENDATA, PRINTPROCESSOROPENDATA, *LPPRINTPROCESSOROPENDATA, *PPRINTPROCESSOROPENDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PRINTPROCESSOROPENDATA
req.alt-loc: winsplp.h
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
req.typenames: PRINTPROCESSOROPENDATA, *LPPRINTPROCESSOROPENDATA, *PPRINTPROCESSOROPENDATA
req.product: Windows 10 or later.
---

# _PRINTPROCESSOROPENDATA structure



## -description
The PRINTPROCESSOROPENDATA structure is used as an input parameter to a print processor's <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a> function.



## -syntax

````
typedef struct _PRINTPROCESSOROPENDATA {
  PDEVMODE pDevMode;
  LPWSTR   pDatatype;
  LPWSTR   pParameters;
  LPWSTR   pDocumentName;
  DWORD    JobId;
  LPWSTR   pOutputFile;
  LPWSTR   pPrinterName;
} PRINTPROCESSOROPENDATA, *PPRINTPROCESSOROPENDATA, *LPPRINTPROCESSOROPENDATA;
````


## -struct-fields

### -field pDevMode

Spooler-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PRINTPROCESSOROPENDATA structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

