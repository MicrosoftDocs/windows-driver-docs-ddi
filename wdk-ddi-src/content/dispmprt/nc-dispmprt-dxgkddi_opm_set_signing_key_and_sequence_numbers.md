---
UID: NC:dispmprt.DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
title: DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
author: windows-driver-content
description: The DxgkDdiOPMSetSigningKeyAndSequenceNumbers function sets the given protected output object's signing key and two sequence numbers.
old-location: display\dxgkddiopmsetsigningkeyandsequencenumbers.htm
old-project: display
ms.assetid: 285521c7-4034-4db8-9441-6c4eaee27ee3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS, Dm_Opm_functions_4ffbc6e2-7239-4c02-88be-aa6276629c7d.xml, DxgkDdiOPMSetSigningKeyAndSequenceNumbers, DxgkDdiOPMSetSigningKeyAndSequenceNumbers callback function [Display Devices], display.dxgkddiopmsetsigningkeyandsequencenumbers, dispmprt/DxgkDdiOPMSetSigningKeyAndSequenceNumbers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiOPMSetSigningKeyAndSequenceNumbers
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback


## -description


The<i> DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> function sets the given protected output object's signing key and two sequence numbers.


## -prototype


````
DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS DxgkDdiOPMSetSigningKeyAndSequenceNumbers;

NTSTATUS DxgkDdiOPMSetSigningKeyAndSequenceNumbers(
  _In_       PVOID                             MiniportDeviceContext,
  _In_       HANDLE                            ProtectedOutputHandle,
  _In_ const PDXGKMDT_OPM_ENCRYPTED_PARAMETERS EncryptedParameters
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


### -param PDXGKMDT_OPM_ENCRYPTED_PARAMETERS








#### - EncryptedParameters [in]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md">DXGKMDT_OPM_ENCRYPTED_PARAMETERS</a> structure that contains a 256-byte array. The array contains between 40 and 256 bytes of data that is encrypted with the public key from the appropriate certificate. For more information about the public key, download the Output Content Protection document at the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website. If the protected output has OPM semantics, the data is encrypted with the public key from the display miniport driver's OPM certificate. If the protected output has Certified Output Protection Protocol (COPP) semantics, the data is encrypted with the public key from the display miniport driver's COPP certificate. 

The algorithm that the display miniport driver should use to decrypt the data in the array depends on the semantics of the protected output. Protected outputs with OPM semantics use the RSAES-OAEP encryption scheme to decrypt the data. For more information about RSAES-OAEP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. Protected outputs with COPP semantics use the standard RSA encryption algorithm to decrypt the encrypted data. 

After the display miniport driver decrypts the data, only the first 40 bytes of the data is currently useful. The first 16 bytes of the decrypted data contain the random number that the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> function returned when the handle in the <i>ProtectedOutputHandle</i> parameter was passed to it. The next 16 bytes contain the 128-bit AES signing key. The next 4 bytes contain the sequence number that is used by <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>. The final 4 bytes contain the sequence number that is used by <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>. The remainder of the decrypted data should be ignored if it exists. 


## -returns



<i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function successfully set the signing key and two sequence numbers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OPM_INVALID_ENCRYPTED_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> returns this value for one of the following reasons: 

<ul>
<li>
If the protected output has OPM semantics, the data that the display miniport driver decrypted was not encoded with the RSAES-OAEP encoding algorithm. For more information about RSAES-OAEP, see section 7.1.2 in the PKCS #1 v2.1: RSA Cryptography Standard, at the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. 

</li>
<li>
The data was not encrypted by the caller with the appropriate public key. If the output has OPM semantics, the caller should encrypt the data with the public key from the display miniport driver's OPM certificate. If the output has COPP semantics, the caller should encrypt the data with the public key from the display miniport driver's COPP certificate.

</li>
<li>
The caller did not encrypt at least 40 bytes of data.

</li>
<li>
The 16-byte random number in the data that the display miniport driver decrypted did not match the 16-byte random number that the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> function returned.

</li>
</ul>
</td>
</tr>
</table>
 

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



The signing key is used to verify that data that is passed to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> functions comes from the application that indirectly uses the protected output. The signing key is also used to sign the data that is returned by the <b>DxgkDdiOPMGetInformation</b> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> functions. One of the sequence numbers is used by <i>DxgkDdiOPMConfigureProtectedOutput</i>. The other sequence number is used by <i>DxgkDdiOPMGetInformation</i> or <i>DxgkDdiOPMGetCOPPCompatibleInformation</i>.

<i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> should return a failure code if an error occurs or if the data in the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md">DXGKMDT_OPM_ENCRYPTED_PARAMETERS</a> structure that is pointed to by the <i>EncryptedParameters</i> parameter is not in the required format. Otherwise, <i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> should perform the following sequence of operations:

<ol>
<li>
Decrypt the data that is pointed to by <i>EncryptedParameters</i> with the appropriate private key and encryption scheme. If the output has OPM semantics, the display miniport driver should use its OPM private key to decrypt the data. If the output has COPP semantics, the display miniport driver should use its COPP private key to decrypt the data. 

</li>
<li>
If the output has OPM semantics, verify that the data that was decrypted was encoded with the RSAES-OAEP encoding algorithm. 

</li>
<li>
Verify that at least 40 bytes of the data was decrypted.

</li>
<li>
Verify that the random number that is contained in the first 16 bytes of the data that was decrypted matches the random number that the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> returned when the handle in the <i>ProtectedOutputHandle</i> parameter was passed to it.

</li>
<li>
Cache the 128-bit AES signing key and the two 32-bit sequence numbers.

</li>
</ol>
Before a protected output object's handle is passed to <i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i>, it is passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>. Each protected output object handle is only passed to <i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> once.

<i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> should be made pageable.

<h3><a id="rsaes_oaep_and_mgf1_parameters"></a><a id="RSAES_OAEP_AND_MGF1_PARAMETERS"></a>RSAES-OAEP and MGF1 Parameters</h3>
RSAES-OAEP is a parameterized encryption scheme and MGF1 is a parameterized mask generation function. Following are the parameters OPM uses when it uses RSAES-OAEP and MGF1. For more information about the following terms and the RSA Cryptography Standard, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=70462">Secure Hashing</a> websites.






## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md">DXGKMDT_OPM_ENCRYPTED_PARAMETERS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

