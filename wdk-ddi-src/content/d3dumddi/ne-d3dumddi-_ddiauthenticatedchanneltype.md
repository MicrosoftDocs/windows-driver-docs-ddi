---
UID: NE:d3dumddi._DDIAUTHENTICATEDCHANNELTYPE
title: "_DDIAUTHENTICATEDCHANNELTYPE"
author: windows-driver-content
description: The DDIAUTHENTICATEDCHANNELTYPE enumeration contains values that identify authenticated-channel types.
old-location: display\ddiauthenticatedchanneltype.htm
old-project: display
ms.assetid: 431575b7-1173-448c-98a9-790bc2721da0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D_other_Structs_ac5c5f50-3e64-483f-86d1-a0cd99f0578b.xml, DDIAUTHENTICATEDCHANNELTYPE, DDIAUTHENTICATEDCHANNELTYPE enumeration [Display Devices], DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE, DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE, _DDIAUTHENTICATEDCHANNELTYPE, d3dumddi/DDIAUTHENTICATEDCHANNELTYPE, d3dumddi/DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE, d3dumddi/DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE, display.ddiauthenticatedchanneltype
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DDIAUTHENTICATEDCHANNELTYPE
product:
- Windows
targetos: Windows
req.typenames: DDIAUTHENTICATEDCHANNELTYPE
---

# _DDIAUTHENTICATEDCHANNELTYPE enumeration


## -description


The DDIAUTHENTICATEDCHANNELTYPE enumeration contains values that identify authenticated-channel types. 


## -enum-fields




### -field DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE

The value specifies that the authenticated-channel type is software. 


### -field DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE

The value specifies that the authenticated-channel type is hardware.


## -remarks



The user-mode display driver receives a DDIAUTHENTICATEDCHANNELTYPE-typed value in the <b>ChannelType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549552">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure points to this DDICERTIFICATEINFO structure when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. 

The Microsoft Direct3D runtime specifies a DDIAUTHENTICATEDCHANNELTYPE-typed value in the <b>ChannelType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542918">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure that the <i>pData</i> parameter points to in a call to the driver's <a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a> function.




## -see-also




<a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542918">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549552">DDICERTIFICATEINFO</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

