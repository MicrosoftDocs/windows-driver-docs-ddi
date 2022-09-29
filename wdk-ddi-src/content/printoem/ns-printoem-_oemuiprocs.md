---
UID: NS:printoem._OEMUIPROCS
title: OEMUIPROCS (printoem.h)
description: The OEMUIPROCS structure is obsolete.The OEMUIPROCS structure contains the address of the DrvGetDriverSetting and DrvUpdateUISetting functions that are exported by Microsoft printer drivers.
tech.root: print
ms.date: 08/12/2022
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
 - _OEMUIPROCS
 - POEMUIPROCS
 - OEMUIPROCS
---

## -description

The **OEMUIPROCS** structure is obsolete.

The **OEMUIPROCS** structure contains the address of the [DrvGetDriverSetting](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvgetdriversetting) and [DrvUpdateUISetting](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvupdateuisetting) functions that are exported by Microsoft printer drivers.

## -struct-fields

### -field DrvGetDriverSetting

Pointer to the printer driver's **DrvGetDriverSetting** function. (To obtain this function's address in kernel mode, see [DRVPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs).

### -field DrvUpdateUISetting

Pointer to the printer driver's **DrvUpdateUISetting** function.

## -remarks

[DrvGetDriverSetting](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvgetdriversetting) and [DrvUpdateUISetting](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvupdateuisetting) have been superseded by COM-based interfaces.

The **OEMUIPROCS** structure's address is contained in an [OEMUIOBJ](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj) structure.
