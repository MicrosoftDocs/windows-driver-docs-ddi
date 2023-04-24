---
UID: NF:winddiui.DrvQueryColorProfile
title: DrvQueryColorProfile function (winddiui.h)
description: The DrvQueryColorProfile function allows a printer interface DLL to specify an ICC profile to use for color management.
tech.root: print
ms.date: 03/09/2023
keywords: ["DrvQueryColorProfile function"]
ms.keywords: DrvQueryColorProfile, DrvQueryColorProfile function [Print Devices], print.drvquerycolorprofile, print_interface-graphics_fce84759-2add-41bc-b4e5-c2b66e3abf04.xml, winddiui/DrvQueryColorProfile
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
 - DrvQueryColorProfile
 - winddiui/DrvQueryColorProfile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvQueryColorProfile
---

## -description

The **DrvQueryColorProfile** function allows a printer interface DLL to specify an ICC profile to use for color management.

## -parameters

### -param hPrinter

Caller-supplied printer handle.

### -param pdevmode [in]

Caller-supplied pointer to a [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure.

### -param ulQueryMode

One of the following caller-supplied bit flags, indicating the type of profile to be specified.

| Flag | Definition |
|---|---|
| QCP_DEVICEPROFILE | The caller is requesting a device profile. |
| QCP_SOURCEPROFILE | The caller is requesting a source profile. |

### -param pvProfileData [out]

Caller-supplied pointer to a buffer to receive profile information.

### -param pcbProfileData [out]

Caller-supplied pointer to a value representing the size, in bytes, of the buffer pointed to by **pvProfileData**.

### -param pflProfileData [out]

One of the following function-supplied bit flags, indicating the type of information the function is returning.

| Flag | Definition |
|---|---|
| QCP_PROFILEDISK | The function is returning the file name of an ICC profile in the buffer pointed to by *pvProfileData*. |
| QCP_PROFILEMEMORY | The function is returning profile data in the buffer pointed to by *pvProfileData*. |

## -returns

If the operation succeeds, the function returns **TRUE**; otherwise, it returns **FALSE**.

## -remarks

A [printer interface DLL](/windows-hardware/drivers/print/printer-interface-dll) can optionally provide a **DrvQueryColorProfile** function. If the function is provided, GDI calls it if ICM has been enabled for a print job. The function's purpose is to determine and specify an ICC profile that is appropriate for use with the print job.

If a driver's printer interface DLL does not provide a **DrvQueryColorProfile** function, or if the function returns **FALSE**, GDI attempts to find a profile. For more information, see [Locating ICC Profiles](/windows-hardware/drivers/print/locating-icc-profiles).

If the output buffer size specified by **pcbProfileData** is too small, the driver should overwrite the size value supplied by **pcbProfileData** with the required buffer size, call SetLastError(ERROR_INSUFFICIENT_BUFFER), and return **FALSE**.
