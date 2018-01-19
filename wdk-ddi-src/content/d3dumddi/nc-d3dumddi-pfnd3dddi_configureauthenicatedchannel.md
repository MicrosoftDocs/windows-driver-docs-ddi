---
UID: NC:d3dumddi.PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL
title: PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL
author: windows-driver-content
description: The ConfigureAuthenticatedChannel function sets state within an authenticated channel.
old-location: display\configureauthenticatedchannel.htm
old-project: display
ms.assetid: 95485e96-fa4f-4c88-b88b-97b79f507abd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: ConfigureAuthenticatedChannel is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ConfigureAuthenticatedChannel
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

# PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL callback



## -description
The <b>ConfigureAuthenticatedChannel</b> function sets state within an authenticated channel. 



## -prototype

````
PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL ConfigureAuthenticatedChannel;

__checkReturn HRESULT APIENTRY ConfigureAuthenticatedChannel(
  _In_          HANDLE                                  hDevice,
  _Inout_ const D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_configureauthenicatedchannel.md">D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL</a> structure that describes how to configure an authenticated channel. This structure contains an input buffer that describes how to configure the authenticated channel and an output buffer with configuration information. 


## -returns
<b>ConfigureAuthenticatedChannel</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The authenticated channel is successfully configured. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> could not allocate the required memory for it to complete.

 


## -remarks
The input buffer contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) that the driver must authenticate. The input buffer also contains the driver's handle to the authenticated channel, a sequence number, and a GUID that indicates the configuration type.

The driver should fail <b>ConfigureAuthenticatedChannel</b> if the input OMAC does not match, if the sequence number is not greater than a sequence number that was specified in a previous call, or if the sequence number has not yet been initialized (the exception to this last rule is for the initialization call itself). 

The driver should duplicate the input data in the structure of the output buffer and should sign the output structure identically to how it currently handles <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) queries.

Except for those situations in which the application incorrectly specifies an output buffer that is too small, the driver should always place the return code in the output structure. Therefore, the application has a secure mechanism to determine the return code. 

<b>ConfigureAuthenticatedChannel</b> performs different operations depending on each of following GUIDs that is specified in the input structure. The driver should fail if the input buffer size does not match the size that is defined for the specified GUID. 



The driver initializes the sequence numbers for the query and the configuration calls. This command can only be sent once per authenticated channel. The driver's <b>ConfigureAuthenticatedChannel</b> function with D3DAUTHETICATEDCONFIGURE_INITIALIZE set should fail if it is called multiple times. The driver can ignore the input sequence number. 

This configuration can be made for all channel types. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_CONFIGUREINITIALIZE structure. 

The driver enables or disables protection for a device. 

The driver should not allow protections that are set by one authenticated channel to be disabled by a different authenticated channel. 

If an application specified the <b>OverlayOrFullscreenRequired</b> protection, the driver should prevent the protected content from ever being rendered to a swap chain unless the protected content is either an overlay swap chain or unless the swapchain is using full-screen flipping mode.

The input buffer points to a D3DAUTHENTICATEDCHANNEL_CONFIGUREPROTECTION  structure.

The driver associates a crypto session with a DirectX Video Acceleration (VA) decode device and a display device. The runtime can later query this crypto session to determine which outputs are associated with the crypto session. For more information about associating a crypto session with a DirectX VA decode device, see <a href="https://msdn.microsoft.com/2a3577f5-bc44-4e0d-a5fa-217dc6c6f5f3">Using Crypto Session with DirectX Video Accelerator 2.0 Decoder</a>.

The driver's <b>ConfigureAuthenticatedChannel</b> function with D3DAUTHETICATEDCONFIGURE_CRYPTOSESSION set should fail if the display device that is specified is not the same device that is used to create the authenticated channel, the crypto session, or the DirectX VA decode device. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_CONFIGURECRYPTOSESSION structure. 

The driver adds and removes processes that can open the shared resources that were created with restricted access. The Desktop Windows Manager (DWM) process is identified by type rather than by process handle because other applications cannot obtain a process handle to the DWM process. 

This configuration can only be made for channel type D3DDDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE. 

The input buffer points to a D3DAUTHENTICATEDCHANNEL_CONFIGURESHAREDRESOURCE structure. 


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_configureauthenicatedchannel.md">D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

