---
UID: NC:d3dumddi.PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL
title: PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: The DestroyAuthenticatedChannel function releases resources for the authenticated channel that the CreateAuthenticatedChannel function creates.
old-location: display\destroyauthenticatedchannel.htm
old-project: display
ms.assetid: ccea427b-e19e-433b-91b0-b40ce7c1da5a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyauthenticatedchannel, DestroyAuthenticatedChannel callback function [Display Devices], DestroyAuthenticatedChannel, PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL, PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL, d3dumddi/DestroyAuthenticatedChannel, UserModeDisplayDriver_Functions_94df7fa0-966d-45e3-81b7-bae1f6ebac64.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyAuthenticatedChannel is supported beginning with the Windows 7 operating system.
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
-	DestroyAuthenticatedChannel
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL callback


## -description


The <b>DestroyAuthenticatedChannel</b> function releases resources for the authenticated channel that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function creates. 


## -prototype


````
PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL DestroyAuthenticatedChannel;

__checkReturn HRESULT APIENTRY DestroyAuthenticatedChannel(
  _In_       HANDLE                                hDevice,
  _In_ const D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroyauthenicatedchannel.md">D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL</a> structure that contains one member that specifies the handle to the authenticated channel to destroy. 


## -returns


<b>DestroyAuthenticatedChannel</b> returns one of the following values:
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
The authenticated channel is successfully destroyed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table> 



## -remarks


The driver's <b>DestroyAuthenticatedChannel</b> function should disable any protections that were set through calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function with the D3DAUTHETICATEDCONFIGURE_PROTECTION and D3DAUTHENTICATEDCONFIGURE_ENCRYPTIONWHENACCESIBLE GUIDs set. However, the driver should not disable shared surface protection (D3DAUTHETICATEDCONFIGURE_SHAREDRESOURCE).



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroyauthenicatedchannel.md">D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

