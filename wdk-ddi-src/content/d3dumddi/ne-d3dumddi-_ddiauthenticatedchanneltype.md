---
UID: NE:d3dumddi._DDIAUTHENTICATEDCHANNELTYPE
title: "_DDIAUTHENTICATEDCHANNELTYPE"
author: windows-driver-content
description: The DDIAUTHENTICATEDCHANNELTYPE enumeration contains values that identify authenticated-channel types.
old-location: display\ddiauthenticatedchanneltype.htm
old-project: display
ms.assetid: 431575b7-1173-448c-98a9-790bc2721da0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE, D3D_other_Structs_ac5c5f50-3e64-483f-86d1-a0cd99f0578b.xml, DDIAUTHENTICATEDCHANNELTYPE, display.ddiauthenticatedchanneltype, d3dumddi/DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE, DDIAUTHENTICATEDCHANNELTYPE enumeration [Display Devices], _DDIAUTHENTICATEDCHANNELTYPE, DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE, d3dumddi/DDIAUTHENTICATEDCHANNELTYPE, DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DDIAUTHENTICATEDCHANNELTYPE is supported beginning with the Windows 7 operating system.
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
-	DDIAUTHENTICATEDCHANNELTYPE
product: Windows
targetos: Windows
req.typenames: DDIAUTHENTICATEDCHANNELTYPE
---

# _DDIAUTHENTICATEDCHANNELTYPE enumeration


## -description


The DDIAUTHENTICATEDCHANNELTYPE enumeration contains values that identify authenticated-channel types. 


## -syntax


````
typedef enum _DDIAUTHENTICATEDCHANNELTYPE { 
  DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE  = 2,
  DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE  = 3
} DDIAUTHENTICATEDCHANNELTYPE;
````


## -enum-fields




### -field DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE

The value specifies that the authenticated-channel type is software. 


### -field DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE

The value specifies that the authenticated-channel type is hardware.


## -remarks


The user-mode display driver receives a DDIAUTHENTICATEDCHANNELTYPE-typed value in the <b>ChannelType</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_ddicertificateinfo.md">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure points to this DDICERTIFICATEINFO structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. 

The Microsoft Direct3D runtime specifies a DDIAUTHENTICATEDCHANNELTYPE-typed value in the <b>ChannelType</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createauthenicatedchannel.md">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure that the <i>pData</i> parameter points to in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createauthenicatedchannel.md">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>

<a href="..\d3dumddi\ns-d3dumddi-_ddicertificateinfo.md">DDICERTIFICATEINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDIAUTHENTICATEDCHANNELTYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

