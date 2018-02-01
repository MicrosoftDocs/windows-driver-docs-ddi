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
ms.keywords: display.configureauthenticatedchannel, ConfigureAuthenticatedChannel callback function [Display Devices], ConfigureAuthenticatedChannel, PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL, PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL, d3dumddi/ConfigureAuthenticatedChannel, UserModeDisplayDriver_Functions_183c7dec-91c3-4929-a86d-c648d1b59ceb.xml
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
-	d3dumddi.h
apiname:
-	ConfigureAuthenticatedChannel
product: Windows
targetos: Windows
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


### -param *






#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_configureauthenicatedchannel.md">D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL</a> structure that describes how to configure an authenticated channel. This structure contains an input buffer that describes how to configure the authenticated channel and an output buffer with configuration information. 


## -returns


<b>ConfigureAuthenticatedChannel</b> returns one of the following values:
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
The authenticated channel is successfully configured. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table> 



## -remarks


The input buffer contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) that the driver must authenticate. The input buffer also contains the driver's handle to the authenticated channel, a sequence number, and a GUID that indicates the configuration type.

The driver should fail <b>ConfigureAuthenticatedChannel</b> if the input OMAC does not match, if the sequence number is not greater than a sequence number that was specified in a previous call, or if the sequence number has not yet been initialized (the exception to this last rule is for the initialization call itself). 

The driver should duplicate the input data in the structure of the output buffer and should sign the output structure identically to how it currently handles <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) queries.

Except for those situations in which the application incorrectly specifies an output buffer that is too small, the driver should always place the return code in the output structure. Therefore, the application has a secure mechanism to determine the return code. 

<b>ConfigureAuthenticatedChannel</b> performs different operations depending on each of following GUIDs that is specified in the input structure. The driver should fail if the input buffer size does not match the size that is defined for the specified GUID. 





## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_configureauthenicatedchannel.md">D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

