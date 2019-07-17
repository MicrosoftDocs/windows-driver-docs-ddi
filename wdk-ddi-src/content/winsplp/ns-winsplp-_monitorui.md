---
UID: NS:winsplp._MONITORUI
title: _MONITORUI (winsplp.h)
description: The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls.
old-location: print\monitorui.htm
tech.root: print
ms.assetid: c6701ca4-f3ce-40b9-8582-d70e8b2acde3
ms.date: 04/20/2018
ms.keywords: "*PMONITORUI, MONITORUI, MONITORUI structure [Print Devices], PMONITORUI, PMONITORUI structure pointer [Print Devices], _MONITORUI, print.monitorui, spoolfnc_bcf5298e-b0b6-41c1-9152-9a804234fba9.xml, winsplp/MONITORUI, winsplp/PMONITORUI"
ms.topic: struct
f1_keywords:
 - "winsplp/MONITORUI"
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
- MONITORUI
product:
- Windows
targetos: Windows
req.typenames: MONITORUI, *PMONITORUI
---

# _MONITORUI structure


## -description


The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls.


## -struct-fields




### -field dwMonitorUISize

Size, in bytes, of the MONITORUI structure.


### -field pfnAddPortUI


### -field pfnConfigurePortUI


### -field pfnDeletePortUI


## -remarks



All structure members must be initialized by the port monitor UI DLL. The structure's address is passed to the print spooler as the return value for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-initializeprintmonitorui">InitializePrintMonitorUI</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-initializeprintmonitorui">InitializePrintMonitorUI</a>
 

 

