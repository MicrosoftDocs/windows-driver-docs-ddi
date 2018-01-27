---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL
author: windows-driver-content
description: Creates an authenticated channel object. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.
old-location: display\createauthenticatedchannel1.htm
old-project: display
ms.assetid: 90b43bc3-6569-4799-8be3-e4e60f59164f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createauthenticatedchannel1, CreateAuthenticatedChannel callback function [Display Devices], CreateAuthenticatedChannel, PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL, PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL, d3d10umddi/CreateAuthenticatedChannel
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
-	CreateAuthenticatedChannel
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL callback


## -description


Creates an authenticated channel object. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.


## -prototype


````
PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL CreateAuthenticatedChannel;

HRESULT APIENTRY* CreateAuthenticatedChannel(
  _In_ D3D10DDI_HDEVICE                         hDevice,
  _In_ D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL *pCreateData,
  _In_ D3D11_1DDI_HAUTHCHANNEL                  hAuthChannel,
  _In_ D3D11_1DDI_HRTAUTHCHANNEL                hRTAuthChannel
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCreateData



### -param hAuthChannel [in]

A handle to the driver's private data for the authenticated channel object. For more information, see the Remarks section.


### -param hRTAuthChannel [in]

A handle to the authenticated channel object that the driver should use when it calls back into the Direct3D runtime.


#### - pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createauthenticatedchannel.md">D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure. This structure specifies the attributes of the authenticated channel to be created.


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
The authenticated channel was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

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


The Direct3D runtime calls <i>CreateAuthenticatedChannel(D3D11_1)</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateauthenticatedchannelsize.md">CalcPrivateAuthenticatedChannelSize</a> to determine the size in bytes for the private data that the driver requires for the authenticated channel object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the authentication channel object.

When the runtime  calls <i>CreateAuthenticatedChannel(D3D11_1)</i>, it passes the handle to the private data memory in the <i>hAuthChannel</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the authenticated channel. The driver should fail all subsequent calls that use this created authenticated channel, such as <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiateauthenticatedchannelkeyexchange.md">NegotiateAuthenticatedChannelKeyExchange</a>, if the display device that is specified in those calls is different from the display device that was used to create the authenticated channel. 





## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateauthenticatedchannelsize.md">CalcPrivateAuthenticatedChannelSize</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createauthenticatedchannel.md">D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiateauthenticatedchannelkeyexchange.md">NegotiateAuthenticatedChannelKeyExchange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

