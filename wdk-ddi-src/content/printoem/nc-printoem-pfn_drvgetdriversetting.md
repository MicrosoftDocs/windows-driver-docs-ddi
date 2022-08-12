---
UID: NC:printoem.PFN_DrvGetDriverSetting
title: PFN_DrvGetDriverSetting (printoem.h)
description: The DrvGetDriverSetting function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvGetDriverSetting callback function"]
ms.keywords: DrvGetDriverSetting, DrvGetDriverSetting callback function [Print Devices], PFN_DrvGetDriverSetting, PFN_DrvGetDriverSetting callback, print.drvgetdriversetting, print_obsoletefunctions_655cde75-fc70-4d6c-a7b4-8eb1e068ebd9.xml, printoem/DrvGetDriverSetting
req.header: printoem.h
req.include-header: 
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
req.typenames: 
f1_keywords:
 - PFN_DrvGetDriverSetting
 - printoem/PFN_DrvGetDriverSetting
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvGetDriverSetting
---

## -description

The **DrvGetDriverSetting** function is obsolete.

 Windows 2000 and later printer drivers should use [IPrintOemDriverUI::DrvGetDriverSetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvgetdriversetting), [IPrintCoreUI2::DrvGetDriverSetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreui2-drvgetdriversetting) (UI plug-ins), [IPrintOemDriverUni::DrvGetDriverSetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvgetdriversetting) (Unidrv plug-ins) or [IPrintOemDriverPS::DrvGetDriverSetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverps-drvgetdriversetting) (Pscript plug-ins)

This function pointer type defines the type of the **DrvGetDriverSetting** member of the [OEMUIPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiprocs) and [DRVPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs) structures.

## -parameters

### -param pdriverobj

Defines the **PVOID** parameter *pdriverobj*.

### -param Feature

Defines the **PCSTR** parameter *Feature*.

### -param pOutput

Defines the **PVOID** parameter *pOutput*.

### -param cbSize

Defines the **DWORD** parameter *cbSize*.

### -param pcbNeeded [out, optional]

Defines the **PDWORD** parameter *pcbNeeded*.

### -param pdwOptionsReturned [out, optional]

Defines the **PDWORD** parameter *pdwOptionsReturned*.

## -returns

Returns a **BOOL** value.
