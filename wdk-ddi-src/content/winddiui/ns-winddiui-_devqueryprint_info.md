---
UID: NS:winddiui._DEVQUERYPRINT_INFO
title: _DEVQUERYPRINT_INFO (winddiui.h)
description: The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's DevQueryPrintEx function.
old-location: print\devqueryprint_info.htm
tech.root: print
ms.assetid: c46193f2-4c69-4aed-a063-2225faba9ee1
ms.date: 04/20/2018
ms.keywords: "*PDEVQUERYPRINT_INFO, DEVQUERYPRINT_INFO, DEVQUERYPRINT_INFO structure [Print Devices], PDEVQUERYPRINT_INFO, PDEVQUERYPRINT_INFO structure pointer [Print Devices], _DEVQUERYPRINT_INFO, print.devqueryprint_info, print_interface-graphics_f968cd94-5290-4aab-908b-c0c01d3038a6.xml, winddiui/DEVQUERYPRINT_INFO, winddiui/PDEVQUERYPRINT_INFO"
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
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
- winddiui.h
api_name:
- DEVQUERYPRINT_INFO
product:
- Windows
targetos: Windows
req.typenames: DEVQUERYPRINT_INFO, *PDEVQUERYPRINT_INFO
---

# _DEVQUERYPRINT_INFO structure


## -description


The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff547576">DevQueryPrintEx</a> function.


## -struct-fields




### -field cbSize

Spooler-supplied size, in bytes, of the DEVQUERYPRINT_INFO structure.


### -field Level

Spooler-supplied level of the DEVQUERYPRINT_INFO structure. Currently, this member is always set to 1.


### -field hPrinter

Spooler-supplied printer handle.


### -field pDevMode

Spooler-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure describing printer characteristics required by the print job.


### -field pszErrorStr

Spooler-supplied pointer to a buffer to receive a NULL-terminated error text string, if the print job cannot be printed.


### -field cchErrorStr

Spooler-supplied size, in bytes, of the string buffer pointed to by <b>pszErrorStr</b>.


### -field cchNeeded

Driver-supplied length, in bytes, of the error string supplied in the buffer pointed to by <b>pszErrorStr</b>. If the string is too large to fit in the buffer, the string should be truncated, but the untruncated length should be specified here.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547576">DevQueryPrintEx</a>
 

 

