---
UID: NS:d3dumddi._D3DDDIARG_CREATEAUTHENICATEDCHANNEL
title: "_D3DDDIARG_CREATEAUTHENICATEDCHANNEL"
author: windows-driver-content
description: The D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure identifies a channel to create.
old-location: display\d3dddiarg_createauthenticatedchannel.htm
old-project: display
ms.assetid: 00f8fbbc-1a4d-4cfe-8b87-fd70bf5a2d48
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_CREATEAUTHENTICATEDCHANNEL, display.d3dddiarg_createauthenticatedchannel, d3dumddi/D3DDDIARG_CREATEAUTHENTICATEDCHANNEL, UMDisplayDriver_param_Structs_3cdac44d-7cac-43f6-80f5-dd601183fa8b.xml, D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure [Display Devices], _D3DDDIARG_CREATEAUTHENICATEDCHANNEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CREATEAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_CREATEAUTHENTICATEDCHANNEL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_CREATEAUTHENICATEDCHANNEL structure


## -description


The D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure identifies a channel to create. 


## -syntax


````
typedef struct _D3DDDIARG_CREATEAUTHENTICATEDCHANNEL {
  DDIAUTHENTICATEDCHANNELTYPE ChannelType;
  HANDLE                      hChannel;
} D3DDDIARG_CREATEAUTHENTICATEDCHANNEL;
````


## -struct-fields




### -field ChannelType

[in] A <a href="..\d3dumddi\ne-d3dumddi-_ddiauthenticatedchanneltype.md">DDIAUTHENTICATEDCHANNELTYPE</a>-typed value that indicates the channel type to create. This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE (2)

</td>
<td>
The authenticated-channel type is software.

</td>
</tr>
<tr>
<td>
DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE (3)

</td>
<td>
The authenticated-channel type is hardware.

</td>
</tr>
</table>
 


### -field hChannel

[out] A handle to the channel. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function returns this handle to the Microsoft Direct3D runtime. 


## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_ddiauthenticatedchanneltype.md">DDIAUTHENTICATEDCHANNELTYPE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

