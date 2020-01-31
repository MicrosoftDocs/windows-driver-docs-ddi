---
UID: NF:fwpsk.FwpsQueryConnectionSioFormatRedirectRecords0
title: FwpsQueryConnectionSioFormatRedirectRecords0 function (fwpsk.h)
description: The FwpsQueryConnectionSioFormatRedirectRecords0 function returns the connection redirect records for a redirected connection.
old-location: netvista\fwpsqueryconnectionsioformatredirectrecords0.htm
tech.root: netvista
ms.assetid: AE24409D-AA60-4694-8855-AB2B0F6B1635
ms.date: 05/02/2018
ms.keywords: FwpsQueryConnectionSioFormatRedirectRecords0, FwpsQueryConnectionSioFormatRedirectRecords0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsQueryConnectionSioFormatRedirectRecords0, netvista.fwpsqueryconnectionsioformatredirectrecords0
f1_keywords:
 - "fwpsk/FwpsQueryConnectionSioFormatRedirectRecords0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsQueryConnectionSioFormatRedirectRecords0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsQueryConnectionSioFormatRedirectRecords0 function


## -description


The <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> function returns the connection redirect records for a redirected connection. For more information about redirection, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>.<div class="alert"><b>Note</b>  <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> is a specific version of <b>FwpsQueryConnectionSioFormatRedirectRecords</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param RedirectRecords [in]

The redirect records handle that the  ALE_CONNECT_REDIRECT callout function received in the  <i>inMetaValues</i> parameter of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function. This handle can be found in the <b>redirectRecords</b>   member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure.

A WFP redirect record is a buffer of opaque data that WFP must set on an outbound proxy connection so that the redirected connection and the original connection are logically related.


### -param OutputBuffer [out, optional]

A pointer to an output buffer that receives the redirect records. The buffer must be pointer-aligned.


### -param OutputBufferLength [in]

The size, in bytes, of the output buffer.


### -param BytesTransferred [out, optional]

A pointer to a variable that receives the number of bytes that were transferred. If the return value is <b>STATUS_BUFFER_TOO_SMALL</b>, this parameter receives the required buffer size.


## -returns



Returns an NTSTATUS value such as one of the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The output buffer was too small to contain all of the bytes to be transferred. The data transfer failed, and the required buffer size can be found in the <i>BytesTransferred</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>RedirectRecords</i> parameter was null.

</td>
</tr>
</table>
 




## -remarks



The <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> function applies only to local proxies.

For more information about redirection, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>.

The <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> function is designed to be used by a WFP connection redirection callout driver that doesn't accept the redirected connection until it has verified that it is able to connect to the actual remote endpoint.  To do this, the callout driver pends the redirected connection request at the <b>FWPS_LAYER_ALE_CONNECT_REDIRECT_V4</b> or <b>FWPS_LAYER_ALE_CONNECT_REDIRECT_V6</b> layer and calls <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> to retrieve the connection redirect records, which the callout driver then sends to the proxy to be used in a call to   <a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/hh859714(v=vs.85)">SIO_SET_WFP_CONNECTION_REDIRECT_RECORDS</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/hh859713(v=vs.85)">SIO_QUERY_WFP_CONNECTION_REDIRECT_RECORDS (SDK)</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/hh859713(v=vs.85)">SIO_QUERY_WFP_CONNECTION_REDIRECT_RECORDS (WDK)</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/hh859714(v=vs.85)">SIO_SET_WFP_CONNECTION_REDIRECT_RECORDS (SDK)</a>



<a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/hh859714(v=vs.85)">SIO_SET_WFP_CONNECTION_REDIRECT_RECORDS (WDK)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
 

 

