---
UID: NE:d3dumddi._D3DDDI_CERTIFICATETYPE
title: "_D3DDDI_CERTIFICATETYPE"
author: windows-driver-content
description: The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types.
old-location: display\d3dddi_certificatetype.htm
old-project: display
ms.assetid: 0e3835af-0ccf-4f41-96e3-beff5fdecd36
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_CERTIFICATETYPE, D3DDDI_CERTIFICATETYPE enumeration [Display Devices], D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL, D3DDDI_CERTTYPE_CRYPTOSESSION, D3D_other_Structs_88de08de-61df-4401-9a7c-8cace88a545a.xml, _D3DDDI_CERTIFICATETYPE, d3dumddi/D3DDDI_CERTIFICATETYPE, d3dumddi/D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL, d3dumddi/D3DDDI_CERTTYPE_CRYPTOSESSION, display.d3dddi_certificatetype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_CERTIFICATETYPE is supported beginning with the Windows 7 operating system.
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
-	D3DDDI_CERTIFICATETYPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_CERTIFICATETYPE
---

# _D3DDDI_CERTIFICATETYPE enumeration


## -description


The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types. 


## -enum-fields




### -field D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL

The value specifies that the certificate type is an authenticated channel. 


### -field D3DDDI_CERTTYPE_CRYPTOSESSION

The value specifies that the certificate type is an encryption session. 


## -remarks



The user-mode display driver receives a D3DDDI_CERTIFICATETYPE-typed value in the <b>CertificateType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549552">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure points to DDICERTIFICATEINFO when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549552">DDICERTIFICATEINFO</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

