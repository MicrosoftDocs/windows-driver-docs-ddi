---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
author: windows-driver-content
description: Contains output data for the ConfigureAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddi_authenticated_configure_output.htm
old-project: display
ms.assetid: 074e87c9-b57e-48ea-8613-2fe1a70cd9e4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT, D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT structure [Display Devices], D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID, D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID, d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT, display.d3d11_1ddi_authenticated_configure_output
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT structure


## -description


Contains output data for the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function.


## -struct-fields




### -field omac

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406450">D3D11_1DDI_OMAC</a> structure that contains a Message Authentication Code (MAC) of the data. The driver uses Advanced Encryption Standard (AES)-based one-key CBC MAC (OMAC) to calculate this value for the block of data that appears after this structure member.


### -field ConfigureType

A GUID that specifies the command. The following GUIDs are defined.



#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID

Sets the level of encryption that is performed before protected content becomes accessible to the CPU or bus.

Input data: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406347">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID

Associates a cryptographic session with a DirectX Video Acceleration 2 (DXVA-2) decode device and a Direct3D device.

Input data: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406350">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID

Initializes the authenticated channel.



Input data: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406354">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID

Enables or disables protection for the device.



Input data: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406366">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>




#### D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID

Enables a process to open a shared resource, or disables a process from opening shared resources.



Input data: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406369">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>



### -field hChannel

A handle to the authenticated channel. This handle was created through a call to the <a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a> function.


### -field SequenceNumber

The query sequence number.

<div class="alert"><b>Note</b>  The sequence number must increase with each successive call to the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function.</div>
<div> </div>

### -field ReturnCode

The return code that the driver returns when the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function is called.


## -remarks



For information on the usage of this structure, see the Remarks of the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function.




## -see-also




<a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406347">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406350">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406354">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406366">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406369">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406450">D3D11_1DDI_OMAC</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

