---
UID: NS:d3dumddi._DDICERTIFICATEINFO
title: "_DDICERTIFICATEINFO"
author: windows-driver-content
description: The DDICERTIFICATEINFO structure describes information about the certificate that the driver uses.
old-location: display\ddicertificateinfo.htm
old-project: display
ms.assetid: 205936c3-fb5a-48e7-8f13-328563c2f0d2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D_other_Structs_99ca6ef3-fba8-4f57-b0bf-16be3c4f8a77.xml, DDICERTIFICATEINFO, DDICERTIFICATEINFO structure [Display Devices], _DDICERTIFICATEINFO, d3dumddi/DDICERTIFICATEINFO, display.ddicertificateinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DDICERTIFICATEINFO is supported beginning with the Windows 7 operating system.
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
-	DDICERTIFICATEINFO
product: Windows
targetos: Windows
req.typenames: DDICERTIFICATEINFO
---

# _DDICERTIFICATEINFO structure


## -description


The DDICERTIFICATEINFO structure describes information about the certificate that the driver uses. 


## -syntax


````
typedef struct _DDICERTIFICATEINFO {
  D3DDDI_CERTIFICATETYPE      CertificateType;
  DDIAUTHENTICATEDCHANNELTYPE ChannelType;
  GUID                        CryptoSessionType;
} DDICERTIFICATEINFO;
````


## -struct-fields




### -field CertificateType

[in] A <a href="..\d3dumddi\ne-d3dumddi-_d3dddi_certificatetype.md">D3DDDI_CERTIFICATETYPE</a>-typed value that indicates the certificate type.


### -field ChannelType

[in] A <a href="..\d3dumddi\ne-d3dumddi-_ddiauthenticatedchanneltype.md">DDIAUTHENTICATEDCHANNELTYPE</a>-typed value that indicates the authenticated-channel type. 


### -field CryptoSessionType

[in] A GUID that indicates the encryption session. 


## -remarks



The runtime specifies a pointer to a DDICERTIFICATEINFO structure in the <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure--along with the D3DDDICAPS_GETCERTIFICATE value in the <b>Type</b> member of D3DDDIARG_GETCAPS--in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to retrieve the certificate. The runtime also supplies a buffer in the <b>pData</b> member of D3DDDIARG_GETCAPS to hold the certificate. The runtime receives information about the size of the buffer when the runtime calls the driver's <b>GetCaps</b> with the D3DDDICAPS_GETCERTIFICATESIZE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. The driver returns a pointer to the certificate in the supplied buffer. 




## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_d3dddi_certificatetype.md">D3DDDI_CERTIFICATETYPE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dumddi\ne-d3dumddi-_ddiauthenticatedchanneltype.md">DDIAUTHENTICATEDCHANNELTYPE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



 

 


