---
UID: NF:fwpsk.FwpsQueryConnectionRedirectState0
title: FwpsQueryConnectionRedirectState0 function (fwpsk.h)
description: The FwpsQueryConnectionRedirectState0 function returns the connection redirect state.Note  FwpsQueryConnectionRedirectState0 is a specific version of FwpsQueryConnectionRedirectState.
old-location: netvista\fwpsqueryconnectionredirectstate0.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FwpsQueryConnectionRedirectState0 function"]
ms.keywords: FwpsQueryConnectionRedirectState0, FwpsQueryConnectionRedirectState0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsQueryConnectionRedirectState0, netvista.fwpsqueryconnectionredirectstate0
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsQueryConnectionRedirectState0
 - fwpsk/FwpsQueryConnectionRedirectState0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsQueryConnectionRedirectState0
---

# FwpsQueryConnectionRedirectState0 function


## -description

The <b>FwpsQueryConnectionRedirectState0</b> function returns the connection redirect state.<div class="alert"><b>Note</b>  <b>FwpsQueryConnectionRedirectState0</b> is a specific version of <b>FwpsQueryConnectionRedirectState</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>

## -parameters

### -param redirectRecords

The redirect records handle  indicated to ALE_CONNECT_REDIRECT callout by the classify metadata.

### -param redirectHandle

A redirect handle that was previously created by a call to the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsredirecthandlecreate0">FwpsRedirectHandleCreate0</a> function.

### -param redirectContext

An optional handle to the redirect context. If the pointer is specified, and if the connection
     redirect state 
     <a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_connection_redirect_state_">FWPS_CONNECTION_REDIRECT_STATE</a> associated with the injection handle is FWPS_CONNECTION_REDIRECTED_BY_SELF
     or FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF, the redirect context supplied when the connection was redirected
     will be returned.

## -returns

The 
     <b>FwpsQueryConnectionRedirectState0</b> function returns one of the states that are specified in the <a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_connection_redirect_state_">FWPS_CONNECTION_REDIRECT_STATE</a> enumeration.

## -remarks

A callout driver calls the <b>FwpsQueryConnectionRedirectState0</b> function to get the redirect state of a connection. 

If the redirect status is FWPS_CONNECTION_NOT_REDIRECTED, the ALE_CONNECT_REDIRECT callout can proceed to proxy the connection.



If the redirect status is FWPS_CONNECTION_REDIRECTED_BY_SELF, the ALE_CONNECT_REDIRECT callout should return FWP_ACTION_PERMIT/FWP_ACTION_CONTINUE.



If the redirect status is FWPS_CONNECTION_REDIRECTED_BY_OTHER, the ALE_CONNECT_REDIRECT callout could proceed to proxy the connection if it does not trust the other inspector's result.



If the redirect status is FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF, the ALE_CONNECT_REDIRECT callout must not perform redirection even if other inspectors' results are not acceptable. In this case,  it must either permit or block the connection (at the ALE_AUTH_CONNECT layer).

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_connection_redirect_state_">FWPS_CONNECTION_REDIRECT_STATE</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsredirecthandlecreate0">FwpsRedirectHandleCreate0</a>
