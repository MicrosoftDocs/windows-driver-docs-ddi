---
UID: NF:fwpsk.FwpsQueryConnectionSioFormatRedirectRecords0
title: FwpsQueryConnectionSioFormatRedirectRecords0 function
author: windows-driver-content
description: The FwpsQueryConnectionSioFormatRedirectRecords0 function returns the connection redirect records for a redirected connection.
old-location: netvista\fwpsqueryconnectionsioformatredirectrecords0.htm
old-project: netvista
ms.assetid: AE24409D-AA60-4694-8855-AB2B0F6B1635
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FwpsQueryConnectionSioFormatRedirectRecords0 function [Network Drivers Starting with Windows Vista], FwpsQueryConnectionSioFormatRedirectRecords0, fwpsk/FwpsQueryConnectionSioFormatRedirectRecords0, netvista.fwpsqueryconnectionsioformatredirectrecords0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsQueryConnectionSioFormatRedirectRecords0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsQueryConnectionSioFormatRedirectRecords0 function


## -description


The <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> function returns the connection redirect records for a redirected connection. For more information about redirection, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>.<div class="alert"><b>Note</b>  <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> is a specific version of <b>FwpsQueryConnectionSioFormatRedirectRecords</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -syntax


````
NTSTATUS FwpsQueryConnectionSioFormatRedirectRecords0(
  _In_      HANDLE  RedirectRecords,
  _Out_opt_ PVOID   OutputBuffer,
  _In_      SIZE_T  OutputBufferLength,
  _Out_opt_ PSIZE_T BytesTransferred
);
````


## -parameters




### -param RedirectRecords [in]

The redirect records handle that the  ALE_CONNECT_REDIRECT callout function received in the  <i>inMetaValues</i> parameter of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function. This handle can be found in the <b>redirectRecords</b>   member of the <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a> structure.

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

For more information about redirection, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>.

The <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> function is designed to be used by a WFP connection redirection callout driver that doesn't accept the redirected connection until it has verified that it is able to connect to the actual remote endpoint.  To do this, the callout driver pends the redirected connection request at the <b>FWPS_LAYER_ALE_CONNECT_REDIRECT_V4</b> or <b>FWPS_LAYER_ALE_CONNECT_REDIRECT_V6</b> layer and calls <b>FwpsQueryConnectionSioFormatRedirectRecords0</b> to retrieve the connection redirect records, which the callout driver then sends to the proxy to be used in a call to   <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh859714">SIO_SET_WFP_CONNECTION_REDIRECT_RECORDS</a>.



## -see-also

<a href="https://msdn.microsoft.com/E0D7CC1A-8F93-45A0-9543-3F2ACAF352F5">SIO_QUERY_WFP_CONNECTION_REDIRECT_RECORDS (SDK)</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh859714">SIO_SET_WFP_CONNECTION_REDIRECT_RECORDS (WDK)</a>

<a href="https://msdn.microsoft.com/0AC78ED4-A6EC-4D62-919C-1EF7CDE8EE80">SIO_SET_WFP_CONNECTION_REDIRECT_RECORDS (SDK)</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh859713">SIO_QUERY_WFP_CONNECTION_REDIRECT_RECORDS (WDK)</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsQueryConnectionSioFormatRedirectRecords0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

