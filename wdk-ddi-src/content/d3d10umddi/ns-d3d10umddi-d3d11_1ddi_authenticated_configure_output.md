---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT (d3d10umddi.h)
description: Contains output data for the ConfigureAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddi_authenticated_configure_output.htm
ms.assetid: 074e87c9-b57e-48ea-8613-2fe1a70cd9e4
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT structure"]
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT, D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT structure [Display Devices], D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID, d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT, display.d3d11_1ddi_authenticated_configure_output
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT"
 - "D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT structure


## -description


Contains output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function.


## -struct-fields




### -field omac

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_omac">D3D11_1DDI_OMAC</a> structure that contains a Message Authentication Code (MAC) of the data. The driver uses Advanced Encryption Standard (AES)-based one-key CBC MAC (OMAC) to calculate this value for the block of data that appears after this structure member.


### -field ConfigureType

A GUID that specifies the command. The following GUIDs are defined.



#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID

Sets the level of encryption that is performed before protected content becomes accessible to the CPU or bus.

Input data: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID

Associates a cryptographic session with a DirectX Video Acceleration 2 (DXVA-2) decode device and a Direct3D device.

Input data: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID

Initializes the authenticated channel.



Input data: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID

Enables or disables protection for the device.



Input data: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID

Enables a process to open a shared resource, or disables a process from opening shared resources.



Input data: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>



### -field hChannel

A handle to the authenticated channel. This handle was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a> function.


### -field SequenceNumber

The query sequence number.

<div class="alert"><b>Note</b>  The sequence number must increase with each successive call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function.</div>
<div> </div>

### -field ReturnCode

The return code that the driver returns when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function is called.


## -remarks



For information on the usage of this structure, see the Remarks of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_omac">D3D11_1DDI_OMAC</a>
 

 

