---
UID: NS:printoem._OEMUIPROCS
title: _OEMUIPROCS (printoem.h)
description: The OEMUIPROCS structure is obsolete.The OEMUIPROCS structure contains the address of the DrvGetDriverSetting and DrvUpdateUISetting functions that are exported by Microsoft printer drivers.
old-location: print\oemuiprocs.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["OEMUIPROCS structure"]
ms.keywords: "*POEMUIPROCS, OEMUIPROCS, OEMUIPROCS structure [Print Devices], POEMUIPROCS, POEMUIPROCS structure pointer [Print Devices], _OEMUIPROCS, print.oemuiprocs, print_unidrv-pscript_ui_2252155b-8f63-4c0f-886b-c66b26ccdd5f.xml, printoem/OEMUIPROCS, printoem/POEMUIPROCS"
req.header: printoem.h
req.include-header: Printoem.h
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
targetos: Windows
req.typenames: OEMUIPROCS, *POEMUIPROCS
f1_keywords:
 - _OEMUIPROCS
 - printoem/_OEMUIPROCS
 - POEMUIPROCS
 - printoem/POEMUIPROCS
 - OEMUIPROCS
 - printoem/OEMUIPROCS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMUIPROCS
---

# _OEMUIPROCS structure


## -description

The OEMUIPROCS structure is obsolete.

The OEMUIPROCS structure contains the address of the <a href="/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvgetdriversetting">DrvGetDriverSetting</a> and <a href="/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvupdateuisetting">DrvUpdateUISetting</a> functions that are exported by Microsoft printer drivers.

## -struct-fields

### -field DrvGetDriverSetting

Pointer to the printer driver's <b>DrvGetDriverSetting</b> function. (To obtain this function's address in kernel mode, see <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a>.)

### -field DrvUpdateUISetting

Pointer to the printer driver's <b>DrvUpdateUISetting</b> function.

## -remarks

<a href="/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvgetdriversetting">DrvGetDriverSetting</a> and <a href="/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvupdateuisetting">DrvUpdateUISetting</a> have been superseded by COM-based interfaces. 

The OEMUIPROCS structure's address is contained in an <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.
