---
UID: NF:fwpmk.FwpmEngineOpen0
title: FwpmEngineOpen0 function (fwpmk.h)
description: The FwpmEngineOpen0 function opens a session to the filter engine.Note  FwpmEngineOpen0 is a specific version of FwpmEngineOpen.
old-location: netvista\fwpmengineopen0.htm
tech.root: netvista
ms.assetid: 4d805ffe-7cf9-4cbc-9077-e191ddc24ecd
ms.date: 05/02/2018
keywords: ["FwpmEngineOpen0 function"]
ms.keywords: FwpmEngineOpen0, FwpmEngineOpen0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmEngineOpen0, netvista.fwpmengineopen0, wfp_ref_2_funct_2_fwpm_29969a12-e73c-4b61-b940-e0da4b0be737.xml
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
 - FwpmEngineOpen0
 - fwpmk/FwpmEngineOpen0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpmEngineOpen0
---

# FwpmEngineOpen0 function


## -description

The **FwpmEngineOpen0** function opens a session to the filter engine.
> [!Note]
> **FwpmEngineOpen0** is a specific version of **FwpmEngineOpen**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -parameters

### -param serverName 

[in, optional]
A pointer to a NULL-terminated string that specifies the standard DNS name of the system on which the session to the filter engine is opened. Callout drivers must specify <b>NULL</b> for this parameter.

### -param authnService 

[in]
The authentication service to use. For a list of valid choices for this parameter, see Authentication-Service Constants in the RPC section in the Microsoft Windows SDK documentation. Callout drivers must specify either RPC_C_AUTHN_WINNT or RPC_C_AUTHN_DEFAULT for this parameter.

### -param authIdentity 

[in, optional]
A pointer to a **SEC_WINNT_AUTH_IDENTITY_W** structure that contains the authentication and authorization credentials for accessing the filter engine. This parameter is ignored when the **FwpmEngineOpen0** function is called from a callout driver. Callout drivers should set this parameter to **NULL**.

### -param session 

[in, optional]
A pointer to an [FWPM_SESSION0](/previous-versions/windows/hardware/drivers/ff550083(v=vs.85)) structure that defines session-specific parameters for the session being opened. This pointer is optional and can be **NULL**.

### -param engineHandle 

[out]
A pointer to a variable that receives a handle for the open session to the filter engine.

## -returns

The **FwpmEngineOpen0** function returns one of the following NTSTATUS codes.

|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|A session to the filter engine was successfully opened. The variable pointed to by the _engineHandle_ parameter contains a handle for the open session.|
|**Other status codes**|An error occurred.|

## -remarks

A callout driver calls the **FwpmEngineOpen0** function to open a session to the filter engine. A handle to an open session to the
filter engine is a required parameter to most of the [Windows Filtering Platform management functions](/windows/win32/fwp/fwp-mgmt-functions).

Callout drivers normally do not need to open a session to the filter engine because callout drivers typically do not call any of the [Windows Filtering Platform](/windows/desktop/FWP/windows-filtering-platform-start-page) management functions.

For a callout driver to successfully open a session to the filter engine, the filter engine must be currently running at the time that the callout driver calls the **FwpmEngineOpen0** function. A callout driver can call the [FwpmBfeStateGet0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateget0) function to obtain the current state of the filter engine. Before calling **FwpmBfeStateGet0**, the callout driver must call the [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0) function to register a callback function that will be called whenever there is a change in the state of the filter engine.

After a callout driver has finished accessing the filter engine, it calls the [FwpmEngineClose0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineclose0) function to close the open session to the filter engine.

## -see-also

[FwpmBfeStateGet0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateget0)



[FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0)



[FwpmCalloutAdd0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutadd0)



[FwpmCalloutDeleteById0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebyid0)



[FwpmCalloutDeleteByKey0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebykey0)



[FwpmEngineClose0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineclose0)



[Other Windows Filtering Platform Functions](/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions)