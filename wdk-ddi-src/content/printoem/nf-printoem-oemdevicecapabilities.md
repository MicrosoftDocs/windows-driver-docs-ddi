---
UID: NF:printoem.OEMDeviceCapabilities
title: OEMDeviceCapabilities function (printoem.h)
description: Describes the OEMDeviceCapabilities function.
tech.root: print
ms.date: 08/08/2022
keywords: ["OEMDeviceCapabilities function"]
ms.keywords: OEMDeviceCapabilities, OEMDeviceCapabilities function [Print Devices], print.oemdevicecapabilities, print_obsoletefunctions_7ab2cfd8-e7cd-4f7c-be2d-a53dbb3651c9.xml, printoem/OEMDeviceCapabilities
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
req.typenames: 
f1_keywords:
 - OEMDeviceCapabilities
 - printoem/OEMDeviceCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMDeviceCapabilities
---

## -description

Describes the **OEMDeviceCapabilities** function.

## -parameters

### -param poemuiobj

Defines the **POEMUIOBJ** parameter *poemuiobj*.

### -param hPrinter

Defines the **HANDLE** parameter *hPrinter*.

### -param pDeviceName

Defines the **PWSTR** parameter *pDeviceName*.

### -param wCapability

Defines the **WORD** parameter *wCapability*.

### -param pOutput

Defines the **PVOID** parameter *pOutput*.

### -param pPublicDM

Defines the **PDEVMODE** parameter *pPublicDM*.

### -param pOEMDM

Defines the **PVOID** parameter *pOEMDM*.

### -param dwLastResult

Defines the **DWORD** parameter *dwLastResult*.

## -returns

Returns a **DWORD** value.
