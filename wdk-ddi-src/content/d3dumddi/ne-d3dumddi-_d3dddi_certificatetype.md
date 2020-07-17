---
UID: NE:d3dumddi._D3DDDI_CERTIFICATETYPE
title: _D3DDDI_CERTIFICATETYPE (d3dumddi.h)
description: The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types.
old-location: display\d3dddi_certificatetype.htm
tech.root: display
ms.assetid: 0e3835af-0ccf-4f41-96e3-beff5fdecd36
ms.date: 05/10/2018
keywords: ["_D3DDDI_CERTIFICATETYPE enumeration"]
ms.keywords: D3DDDI_CERTIFICATETYPE, D3DDDI_CERTIFICATETYPE enumeration [Display Devices], D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL, D3DDDI_CERTTYPE_CRYPTOSESSION, D3D_other_Structs_88de08de-61df-4401-9a7c-8cace88a545a.xml, _D3DDDI_CERTIFICATETYPE, d3dumddi/D3DDDI_CERTIFICATETYPE, d3dumddi/D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL, d3dumddi/D3DDDI_CERTTYPE_CRYPTOSESSION, display.d3dddi_certificatetype
f1_keywords:
 - "d3dumddi/D3DDDI_CERTIFICATETYPE"
 - "D3DDDI_CERTIFICATETYPE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDI_CERTIFICATETYPE
product:
- Windows
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



The user-mode display driver receives a D3DDDI_CERTIFICATETYPE-typed value in the <b>CertificateType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_ddicertificateinfo">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a> structure points to DDICERTIFICATEINFO when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_ddicertificateinfo">DDICERTIFICATEINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

