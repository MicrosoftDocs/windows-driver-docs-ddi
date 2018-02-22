---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
author: windows-driver-content
description: Contains input data for the ConfigureAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddi_authenticated_configure_input.htm
old-project: display
ms.assetid: a481fb2d-60bb-441d-998d-acb983b2c0ed
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT, D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT structure [Display Devices], D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID, display.d3d11_1ddi_authenticated_configure_input, D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT structure


## -description


Contains input data for the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT {
  D3D11_1DDI_OMAC omac;
  GUID            ConfigureType;
  HANDLE          hChannel;
  UINT            SequenceNumber;
} D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT;
````


## -struct-fields




### -field omac

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_omac.md">D3D11_1DDI_OMAC</a> structure that contains a Message Authentication Code (MAC) of the data. The driver uses Advanced Encryption Standard (AES)-based one-key CBC MAC (OMAC) to calculate this value for the block of data that appears after this structure member.


### -field ConfigureType

A GUID that specifies the command. The following GUIDs are defined.



#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID

Sets the level of encryption that is performed before protected content becomes accessible to the CPU or bus.

Input data: <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID

Associates a cryptographic session with a DirectX Video Acceleration 2 (DXVA-2) decode device and a Direct3D device.

Input data: <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID

Initializes the authenticated channel.



Input data: <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID

Enables or disables protection for the device.



Input data: <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID

Enables a process to open a shared resource, or disables a process from opening shared resources.



Input data: <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>



### -field hChannel

A handle to the authenticated channel. This handle was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function. 




### -field SequenceNumber

The query sequence number.

<div class="alert"><b>Note</b>  The sequence number must increase with each successive call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.</div>
<div> </div>

## -remarks



For information on the usage of this structure, see the Remarks of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_omac.md">D3D11_1DDI_OMAC</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

