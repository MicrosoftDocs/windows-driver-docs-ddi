---
UID: NF:winddiui.DrvDriverEvent
title: DrvDriverEvent function (winddiui.h)
description: The print spooler calls a printer interface DLL's DrvDriverEvent function when the spooler processes driver-specific events that might require action by the printer driver.
tech.root: print
ms.date: 03/09/2023
keywords: ["DrvDriverEvent function"]
ms.keywords: DrvDriverEvent, DrvDriverEvent function [Print Devices], print.drvdriverevent, print_interface-graphics_41c98198-e5b7-4725-9b93-d467ec38e4c3.xml, winddiui/DrvDriverEvent
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - DrvDriverEvent
 - winddiui/DrvDriverEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvDriverEvent
---

## -description

The print spooler calls a printer interface DLL's **DrvDriverEvent** function when the spooler processes driver-specific events that might require action by the printer driver.

## -parameters

### -param dwDriverEvent

Caller-supplied bit flag indicating the event that has occurred. Valid flags are listed in the following table.

| Flag | Definition |
|---|---|
| DRIVER_EVENT_DELETE | The driver is being removed. |
| DRIVER_EVENT_INITIALIZE | The driver has just been installed. |

### -param dwLevel

Caller-supplied value indicating the type of structure pointed to by the *pDriverInfo* parameter, as indicated in the following table.

| *dwLevel* Value | Structure pointed to by *pDriverInfo* |
|---|---|
| 1 | DRIVER_INFO_1 |
| 2 | DRIVER_INFO_2 |
| 3 | DRIVER_INFO_3 |

The DRIVER_INFO_*N* structures are described in the Microsoft Windows SDK documentation.

### -param pDriverInfo [in, optional]

Caller-supplied pointer to a structure whose type is identified by the *dwLevel* parameter.

### -param lParam

Caller-supplied flags. See the following Remarks section.

## -returns

If the operation succeeds, the function should return **TRUE**. Otherwise, it should return **FALSE**.

## -remarks

The optional **DrvDriverEvent** function is called by the spooler's **AddPrinterDriverEx** and **DeletePrinterDriverEx** functions, which are described in the Windows SDK documentation.

The function's purpose is to allow a printer driver's [printer interface DLL](/windows-hardware/drivers/print/printer-interface-dll) to perform operations needed when the driver is installed or removed. A typical operation for this function to perform is to create or remove extra driver-specific files that are not specified as dependent files in a [printer INF file](/windows-hardware/drivers/print/printer-inf-files).

If *dwDriverEvent* is DRIVER_EVENT_DELETE, the *lparam* parameter contains the flags that were specified for the **DeletePrinterDriverEx** function's *dwDeleteFlag* parameter. The *lparam* parameter is not used if *dwDriverEvent* is DRIVER_EVENT_INITIALIZE.

Because the **DrvDriverEvent** function is called in the context of the print spooler, it cannot display a user interface.
