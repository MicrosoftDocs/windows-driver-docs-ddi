---
UID: NC:d3dumddi.PFND3DDDI_QUERYAUTHENTICATEDCHANNEL
title: PFND3DDDI_QUERYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: The QueryAuthenticatedChannel function queries an authenticated channel for capability and state information.
old-location: display\queryauthenticatedchannel.htm
old-project: display
ms.assetid: 13b65b5a-9512-4d67-b629-479bdd74674e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: QueryAuthenticatedChannel is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: QueryAuthenticatedChannel
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_QUERYAUTHENTICATEDCHANNEL callback



## -description
The <i>QueryAuthenticatedChannel</i> function queries an authenticated channel for capability and state information. 



## -prototype

````
PFND3DDDI_QUERYAUTHENTICATEDCHANNEL QueryAuthenticatedChannel;

__checkReturn HRESULT APIENTRY QueryAuthenticatedChannel(
  _In_          HANDLE                              hDevice,
  _Inout_ const D3DDDIARG_QUERYAUTHENTICATEDCHANNEL *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_queryauthenicatedchannel.md">D3DDDIARG_QUERYAUTHENTICATEDCHANNEL</a> structure that describes authenticated-channel information to query. This structure contains an input buffer that describes the query and an output buffer to return the queried information. 


## -returns
<i>QueryAuthenticatedChannel</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The authenticated channel is successfully queried. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>QueryAuthenticatedChannel</i> could not allocate the required memory for it to complete.

 


## -remarks
The input buffer contains the driver's handle to the authenticated channel, a sequence number, and a GUID that indicates the type of query. The driver should fail all queries if the driver did not previously initialize the sequence number through a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function. The driver should also fail the query if the sequence number is not greater than the sequence number of the previous query call. 

The driver should duplicate the input data in the structure of the output buffer and should sign the output structure identically to how it currently handles <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) queries.

Except for those situations in which the application incorrectly specifies an output buffer that is too small, the driver should always place the return code in the output structure. Therefore, the application has a secure mechanism to determine the return code. 

<i>QueryAuthenticatedChannel</i> performs different operations depending on each of following GUIDs that is specified in the input structure. The driver should fail if the input and output buffer sizes do not match the sizes that are defined for the specified GUID. 



The driver returns the current protection level for the device. This query can be used for both software and hardware channels, However, frequently polling the protection level is not required for a DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE channel.

The input buffer points to a D3DAUTHENTICATEDCHANNEL_QUERY_INPUT structure.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYPROTECTION_OUTPUT structure. 

The driver returns the channel type. This query can be made for all channel types. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_QUERY_INPUT structure.  

The output buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYCHANNELTYPE_OUTPUT structure. 

The driver returns a device identifier that the calling application can use to verify that multiple authenticated channels are indeed communicating with the same device. This query can be made for all channel types.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYDEVICEHANDLE_OUTPUT structure. 

The driver returns the crypto session handle (the same handle that the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function returned in the <b>hCryptoSession</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a> structure) and the display device handle (the same handle that the driver's <i>QueryAuthenticatedChannel</i> function returned with the D3DAUTHENTICATEDQUERY_DEVICEHANDLE query) that are currently associated with the DirectX Video Acceleration (DirectX VA) decode device. The handle to the DirectX VA decode device is the same handle that the driver returned in response to the new DXVA2_DECODE_GET_DRIVER_HANDLE decode extension. For more information about DXVA2_DECODE_GET_DRIVER_HANDLE, see <a href="https://msdn.microsoft.com/2a3577f5-bc44-4e0d-a5fa-217dc6c6f5f3">Using Crypto Session with DirectX Video Accelerator 2.0 Decoder</a>.

This query can be made for all channel types.

The input buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYCRYPTOSESSION_INPUT structure.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_ QUERYCRYPTOSESSION_OUTPUT structure. 

While the operating system has a mechanism to restrict access to shared resources, the operating system protections are not robust against harmful code within the process or within the kernel. Therefore, this query exists to allow drivers to provide protections for extra level of robustness. Note that the driver cannot determine for sure which process is the Desktop Windows Manager (DWM) process; therefore, the driver must pick the most appropriate process. 

These driver protections are only required for channel type DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE because hardware protection can prevent resource data from being stolen more securely than these driver protections.

The driver returns the number of processes that are allowed to open the shared resources that were created with restricted access. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_QUERY_INPUT structure. 

The output buffer points to a D3DAUTHENTICATEDCHANNEL_ QUERY RESTRICTEDSHAREDRESOURCEPROCESSCOUNT_OUTPUT structure. 

The driver returns one of the processes that are allowed to open shared resources that were created with restricted access. The total number of these processes is returned with the D3DAUTHENTICATEDQUERY_RESTRICTEDSHAREDRESOURCEPROCESSCOUNT query. The DWM process is referenced by type rather than by process handle because applications cannot obtain a process handle for the DWM. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_ QUERYRESTRICTEDSHAREDRESOURCEPROCESS_INPUT structure.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_ QUERYRESTRICTEDSHAREDRESOURCEPROCESS_OUTPUT structure. 

The driver returns the number of shared resources that were created as protected but are allowed to be opened by any process without restrictions. 

This query can only be made for channel type D3DAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_ QUERYUNRESRICTTEDPROTECTEDSHAREDRESOURCECOUNT_OUTPUT structure. 

The driver uses the OPM interface to enable protections on an individual output. However, OPM gives no assurance that the output that is controlled is the output that contains the protected content. 

This query requests that the driver indicate the number of outputs on which the device presents its content. 

The driver should fail if the crypto session handle that is specified (the same handle that the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function returned in the <b>hCryptoSession</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a> structure) is associated with a different display device than the one that is specified. 

The driver returns the number of output identifiers that is associated with the device and the crypto session. 

This query can be made for all channel types. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYOUTPUTIDCOUNT_INPUT structure.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYOUTPUTIDCOUNT_OUTPUT structure. 

This query requests the driver to return an identifier for each output on which the device presents its content. The number of these outputs is returned with the D3DAUTHENTICATEDQUERY_OUTPUTIDCOUNT query.

A new OPM query (DXGKMDT_OPM_GET_OUTPUT_ID) requests the driver to return the identifier for the output that the driver controls. The application can then ensure that the correct outputs are being managed.

The input buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYOUTPUTID_INPUT structure.

The output buffer points to a D3DAUTHENTICATEDCHANNEL_QUERYROUTPUTID_OUTPUT structure. 


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_queryauthenicatedchannel.md">D3DDDIARG_QUERYAUTHENTICATEDCHANNEL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_QUERYAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

