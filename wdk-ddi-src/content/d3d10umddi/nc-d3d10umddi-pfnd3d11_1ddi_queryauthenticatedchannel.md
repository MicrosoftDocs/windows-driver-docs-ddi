---
UID: NC:d3d10umddi.PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: Queries an authenticated channel for capability and state information. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.
old-location: display\queryauthenticatedchannel1.htm
old-project: display
ms.assetid: bb152e3d-497f-4798-86cc-6f300e24a05c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.queryauthenticatedchannel1, QueryAuthenticatedChannel callback function [Display Devices], QueryAuthenticatedChannel, PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL, PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL, d3d10umddi/QueryAuthenticatedChannel, display.pfnqueryauthenticatedchannel1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	D3d10umddi.h
apiname: 
-	QueryAuthenticatedChannel
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL callback


## -description


Queries an authenticated channel for capability and state information. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.


## -prototype


````
PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL QueryAuthenticatedChannel;

HRESULT APIENTRY* QueryAuthenticatedChannel(
  _In_        D3D10DDI_HDEVICE        hDevice,
  _In_        D3D11_1DDI_HAUTHCHANNEL hCAuthChannel,
  _In_        UINT                    InputDataSize,
  _Out_ const VOID                    *pInputData,
  _In_        UINT                    OutputDataSize,
  _Out_       VOID                    *pOutputData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCAuthChannel [in]

A handle to an authenticated channel object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.


### -param InputDataSize [in]

The size, in bytes, of the data in the <i>pInputData</i> array.




### -param *pInputData



### -param OutputDataSize [in]

The size, in bytes, of the data in the <i>pOutputData</i> array.




### -param *pOutputData






#### - pInputData [out]

A pointer to a buffer that describes the information to query. The data in this buffer is formatted as a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure.


#### - pOutputData [out]

A pointer to a buffer that contains the queried information. For more information, see the Remarks section.


## -returns


Returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The authenticated channel was queried successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support the specified command

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table> 



## -remarks


The <i>pInputData</i> parameter references a buffer that contains a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure. This structure contains the driver's handle to the authenticated channel, a sequence number, and a GUID that indicates the type of query to perform.  The driver must return  <b>E_INVALIDARG</b> if the sequence number was not previously initialized by using the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.  The driver must  also return  <b>E_INVALIDARG</b> if the sequence number is not greater than the sequence number of the previous query call.



The byte array that is referenced by the <i>pOutputData</i> parameter is in a format that is specified by the <b>QueryType</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure. The following list describes the format of this data based on the <b>QueryType</b> member.



The driver prepares the output buffer that is referenced by the <i>pOutputData</i> parameter by following these steps:
<ol>
<li>
Each structure that is returned based on the <b>QueryType</b> member starts with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure. The driver must copy the members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> to the <b>D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</b> structure. 

</li>
<li>
The driver must set the  <b>ReturnCode</b> member to the same return code that it will return for the <i>QueryAuthenticatedChannel(D3D11_1)</i> call. This provides the application with a secure mechanism of accessing the return code. 



</li>
<li>
Based on the value of the <b>QueryType</b> member, the driver must initialize the corresponding structure that follows the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure in the <i>pOutputData</i> buffer.

</li>
<li>
The driver must sign the <i>pOutputData</i> buffer in a way that is identical to the way it handles Output Protection Manager (OPM) queries.

The <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure contains an AES-based one-key CBC message authentication code (OMAC) of the data. The display miniport driver must calculate an OMAC over the data in the output buffer to authenticate the data. The driver does this by first setting the <b>omac</b> member to zero and then calculating an OMAC for the data in the buffer. The driver then sets the <b>omac</b> member to the OMAC that it calculated.

</li>
</ol>The display miniport driver must return  <b>E_INVALIDARG</b> for the <i>QueryAuthenticatedChannel(D3D11_1)</i> call under the following conditions:
<ul>
<li>
The sequence number is not greater than a sequence number that was specified in a previous configuration call.

</li>
<li>
The sequence number has not yet been initialized by a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.



</li>
<li>
The <i>OutputDataSize</i> parameter is less than size of the structure specified by the  <b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.QueryType</b> member.

</li>
</ul>


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_QUERYAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

