---
UID: NF:winspool.IsValidDevmodeW
title: IsValidDevmodeW function (winspool.h)
description: Learn how the print spooler's IsValidDevmode function verifies that the contents of a DEVMODE structure are valid.
tech.root: print
ms.date: 04/20/2022
keywords: ["IsValidDevmodeW function"]
ms.keywords: IsValidDevmode, IsValidDevmode function [Print Devices], IsValidDevmodeA, IsValidDevmodeW, print.isvaliddevmode, spoolfnc_ea9b6cc1-6f0b-42a7-835b-df561588691a.xml, winspool/IsValidDevmode
req.header: winspool.h
req.include-header: Winspool.h
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
req.lib: Winspool.lib
req.dll: Winspool.drv
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IsValidDevmodeW
 - winspool/IsValidDevmodeW
 - IsValidDevmode
 - winspool/IsValidDevmode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Winspool.drv
api_name:
 - IsValidDevmodeW
 - IsValidDevmode
---

## -description

The print spooler's **IsValidDevmode** function verifies that the contents of a [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure are valid.

## -parameters

### -param pDevmode [in, optional]

Pointer to the DEVMODE structure to be validated.

### -param DevmodeSize

Size, in bytes, of the buffer pointed to by *pDevmode*.

## -returns

If the DEVMODE structure is valid, or if the function succeeds in repairing the structure to make it valid, the function returns **TRUE**. Otherwise, the function returns **FALSE**. The caller can obtain an error code by calling **GetLastError**.

## -remarks

Before using a DEVMODE structure obtained from a possibly unreliable source, a printer driver can call this function to verify that the structure is valid. This function validates only the public members of the DEVMODE structure. It does not check the private members of the structure.

The **dmSize** member of the DEVMODE structure specifies the size of the DEVMODE structure, not including any private, driver-specified data appended to the structure. The **dmDriverExtra** member specifies the size of the private data appended to the structure, if there is any. Callers should set *DevModeSize* to **dmSize**+**dmDriverExtra** only if they can guarantee that the input buffer size is at least that large.

This function does not require the caller to obtain elevated privileges.

## -see-also

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodew)
