---
UID: NS:printoem._DRVPROCS
title: DRVPROCS (printoem.h)
description: The DRVPROCS structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers.
tech.root: print
ms.date: 08/12/2022
keywords: ["DRVPROCS structure"]
ms.keywords: "*PDRVPROCS, DRVPROCS, DRVPROCS structure [Print Devices], PDRVPROCS, PDRVPROCS structure pointer [Print Devices], _DRVPROCS, print.drvprocs, print_unidrv-pscript_rendering_63cf2b11-04c8-43f3-951b-5755764059f9.xml, printoem/DRVPROCS, printoem/PDRVPROCS"
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
req.typenames: DRVPROCS, *PDRVPROCS
f1_keywords:
 - _DRVPROCS
 - printoem/_DRVPROCS
 - PDRVPROCS
 - printoem/PDRVPROCS
 - DRVPROCS
 - printoem/DRVPROCS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _DRVPROCS
 - PDRVPROCS
 - DRVPROCS
---

## -description

The **DRVPROCS** structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers.

The structure contains the addresses of helper functions that are provided to rendering plug-ins by Microsoft printer drivers.

All of the functions pointed to by members of this structure are obsolete. For more information about each, see the following topics:

[**DrvWriteSpoolBuf**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvwritespoolbuf)

[**DrvXMoveTo**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvxmoveto)

[**DrvYMoveTo**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvymoveto)

[**DrvGetDriverSetting**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvgetdriversetting)

[**DrvGetStandardVariable**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvgetstandardvariable) (for information about BGetStandardVariable)

[**DrvUnidriverTextOut**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvunidrivertextout)

[**DrvWriteAbortBuf**](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvwriteabortbuf)

## -struct-fields

### -field DrvWriteSpoolBuf

Defines the **PFN_DrvWriteSpoolBuf** member **DrvWriteSpoolBuf**.

### -field DrvXMoveTo

Defines the **PFN_DrvXMoveTo** member **DrvXMoveTo**.

### -field DrvYMoveTo

Defines the **PFN_DrvYMoveTo** member **DrvYMoveTo**.

### -field DrvGetDriverSetting

Defines the **PFN_DrvGetDriverSetting** member **DrvGetDriverSetting**.

### -field BGetStandardVariable

Defines the **PFN_DrvGetStandardVariable** member **BGetStandardVariable**.

### -field DrvUnidriverTextOut

Defines the **PFN_DrvUnidriverTextOut** member **DrvUnidriverTextOut**.

### -field DrvWriteAbortBuf

Defines the **PFN_DrvWriteAbortBuf** member **DrvWriteAbortBuf**.
