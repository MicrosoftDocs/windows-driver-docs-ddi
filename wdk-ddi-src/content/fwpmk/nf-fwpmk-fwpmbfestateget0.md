---
UID: NF:fwpmk.FwpmBfeStateGet0
title: FwpmBfeStateGet0 function (fwpmk.h)
description: The FwpmBfeStateGet0 function retrieves the current state of the filter engine.Note  FwpmBfeStateGet0 is a specific version of FwpmBfeStateGet.
old-location: netvista\fwpmbfestateget0.htm
tech.root: netvista
ms.date: 06/21/2024
keywords: ["FwpmBfeStateGet0 function"]
ms.keywords: FwpmBfeStateGet0, FwpmBfeStateGet0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmBfeStateGet0, netvista.fwpmbfestateget0, wfp_ref_2_funct_2_fwpm_6f70e48b-0c6c-465e-95c3-fa41413398db.xml
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpmBfeStateGet0
 - fwpmk/FwpmBfeStateGet0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fwpkclnt.lib
 - Fwpkclnt.dll
api_name:
 - FwpmBfeStateGet0
---

# FwpmBfeStateGet0 function

## -description

The **FwpmBfeStateGet0** function retrieves the current state of the filter engine.

## -returns

The **FwpmBfeStateGet0** function returns one of the following values.

| Return code | Description |
| --- | --- |
| **FWPM_SERVICE_STOPPED** | The filter engine is not running. |
| **FWPM_SERVICE_START_PENDING** | The filter engine is starting. |
| **FWPM_SERVICE_STOP_PENDING** | The filter engine is stopping. |
| **FWPM_SERVICE_RUNNING** | The filter engine is running. |

## -remarks

A callout driver calls the **FwpmBfeStateGet0** function to retrieve the current state of the filter engine. For a callout driver to open a session to the filter engine, the filter engine must  be currently running.

Before calling **FwpmBfeStateGet0**, the callout driver  must call the [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0) function to register a callback function that is called whenever the state of the filter engine changes.

**FwpmBfeStateGet0** is a specific version of **FwpmBfeStateGet**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0)
