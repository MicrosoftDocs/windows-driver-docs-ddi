---
UID: NF:fwpmk.FwpmEngineClose0
title: FwpmEngineClose0 function (fwpmk.h)
description: The FwpmEngineClose0 function closes a previously opened session to the filter engine.Note  FwpmEngineClose0 is a specific version of FwpmEngineClose.
old-location: netvista\fwpmengineclose0.htm
tech.root: netvista
ms.date: 06/21/2024
keywords: ["FwpmEngineClose0 function"]
ms.keywords: FwpmEngineClose0, FwpmEngineClose0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmEngineClose0, netvista.fwpmengineclose0, wfp_ref_2_funct_2_fwpm_b01feaca-7c4a-44a9-aec4-f867508b0129.xml
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpmEngineClose0
 - fwpmk/FwpmEngineClose0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpmEngineClose0
---

# FwpmEngineClose0 function

## -description

The **FwpmEngineClose0** function closes a previously opened session to the filter engine.

## -parameters

### -param engineHandle [in, out]

A handle for an open session to the filter engine.

## -returns

The **FwpmEngineClose0** function returns one of the following NTSTATUS codes.

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | The session to the filter engine was successfully closed. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

A callout driver calls the **FwpmEngineClose0** function to close a session to the filter engine that was previously opened by a call to the [FwpmEngineOpen0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0) function.

**FwpmEngineClose0** is a specific version of **FwpmEngineClose**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- [FwpmEngineOpen0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0)
