---
UID: NC:dispmprt.DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
title: DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS (dispmprt.h)
description: The DxgkDdiOPMSetSigningKeyAndSequenceNumbers function sets the given protected output object's signing key and two sequence numbers.
old-location: display\dxgkddiopmsetsigningkeyandsequencenumbers.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback function"]
ms.keywords: DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS, DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback, Dm_Opm_functions_4ffbc6e2-7239-4c02-88be-aa6276629c7d.xml, DxgkDdiOPMSetSigningKeyAndSequenceNumbers, DxgkDdiOPMSetSigningKeyAndSequenceNumbers callback function [Display Devices], display.dxgkddiopmsetsigningkeyandsequencenumbers, dispmprt/DxgkDdiOPMSetSigningKeyAndSequenceNumbers
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
 - dispmprt/DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
---

# DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback function


## -description

The **DxgkDdiOPMSetSigningKeyAndSequenceNumbers** function sets the given protected output object's signing key and two sequence numbers.

## -parameters

### -param MiniportDeviceContext

[in] A handle to a context block associated with a display adapter. Previously, the display miniport driver's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function provided this handle to the DirectX graphics kernel subsystem.

### -param ProtectedOutputHandle

[in] The handle to a protected output object. The [**DxgkDdiOPMCreateProtectedOutput**](nc-dispmprt-dxgkddi_opm_create_protected_output.md) function creates the protected output object and returns the handle to the object.

### -param EncryptedParameters

[in] A pointer to a [**DXGKMDT_OPM_ENCRYPTED_PARAMETERS**](..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md) structure that contains a 256-byte array. The array contains between 40 and 256 bytes of data that is encrypted with the public key from the appropriate certificate. For more information about the public key, download the Output Content Protection document from [Supporting Output Protection Manager](/windows-hardware/drivers/display/supporting-output-protection-manager). If the protected output has OPM semantics, the data is encrypted with the public key from the display miniport driver's OPM certificate. If the protected output has Certified Output Protection Protocol (COPP) semantics, the data is encrypted with the public key from the display miniport driver's COPP certificate.

The algorithm that the display miniport driver should use to decrypt the data in the array depends on the semantics of the protected output. Protected outputs with OPM semantics use the RSAES-OAEP encryption scheme to decrypt the data. For more information about RSAES-OAEP, see the [RSA Laboratories](https://www.rsa.com/) website. Protected outputs with COPP semantics use the standard RSA encryption algorithm to decrypt the encrypted data.

After the display miniport driver decrypts the data, only the first 40 bytes of the data is currently useful. The first 16 bytes of the decrypted data contain the random number that the display miniport driver's [**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md) function returned when the handle in the *ProtectedOutputHandle* parameter was passed to it. The next 16 bytes contain the 128-bit AES signing key. The next 4 bytes contain the sequence number that is used by [**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md) or [**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md). The final 4 bytes contain the sequence number that is used by [**DxgkDdiOPMConfigureProtectedOutput**](nc-dispmprt-dxgkddi_opm_configure_protected_output.md). The remainder of the decrypted data should be ignored if it exists.

## -returns

**DxgkDdiOPMSetSigningKeyAndSequenceNumbers** returns **STATUS_SUCCESS** if the function successfully set the signing key and two sequence numbers. Otherwise, it might return **STATUS_OPM_INVALID_ENCRYPTED_PARAMETERS** for one of the following reasons:

* If the protected output has OPM semantics, the data that the display miniport driver decrypted was not encoded with the RSAES-OAEP encoding algorithm. For more information about RSAES-OAEP, see section 7.1.2 in the PKCS #1 v2.1: RSA Cryptography Standard, at the [RSA Laboratories](https://www.rsa.com)  website.
* The data was not encrypted by the caller with the appropriate public key. If the output has OPM semantics, the caller should encrypt the data with the public key from the display miniport driver's OPM certificate. If the output has COPP semantics, the caller should encrypt the data with the public key from the display miniport driver's COPP certificate.
* The caller did not encrypt at least 40 bytes of data.
* The 16-byte random number in the data that the display miniport driver decrypted did not match the 16-byte random number that the [**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md)  function returned.

This function might also return other error codes that are defined in *Ntstatus.h*.

## -prototype

```cpp
DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS DxgkDdiOPMSetSigningKeyAndSequenceNumbers;

NTSTATUS DxgkDdiOPMSetSigningKeyAndSequenceNumbers(
  _In_       PVOID                             MiniportDeviceContext,
  _In_       HANDLE                            ProtectedOutputHandle,
  _In_ const PDXGKMDT_OPM_ENCRYPTED_PARAMETERS EncryptedParameters
)
{ ... }
```

## -remarks

The signing key is used to verify that data that is passed to the [**DxgkDdiOPMConfigureProtectedOutput**](nc-dispmprt-dxgkddi_opm_configure_protected_output.md) and [**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md) functions comes from the application that indirectly uses the protected output. The signing key is also used to sign the data that is returned by the **DxgkDdiOPMGetInformation** and [**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) functions. One of the sequence numbers is used by **DxgkDdiOPMConfigureProtectedOutput**. The other sequence number is used by **DxgkDdiOPMGetInformation** or **DxgkDdiOPMGetCOPPCompatibleInformation**.

**DxgkDdiOPMSetSigningKeyAndSequenceNumbers** should return a failure code if an error occurs or if the data in the [**DXGKMDT_OPM_ENCRYPTED_PARAMETERS**](..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md) structure that is pointed to by the **EncryptedParameters** parameter is not in the required format. Otherwise, **DxgkDdiOPMSetSigningKeyAndSequenceNumbers** should perform the following sequence of operations:

1. Decrypt the data that is pointed to by **EncryptedParameters** with the appropriate private key and encryption scheme. If the output has OPM semantics, the display miniport driver should use its OPM private key to decrypt the data. If the output has COPP semantics, the display miniport driver should use its COPP private key to decrypt the data.
2. If the output has OPM semantics, verify that the data that was decrypted was encoded with the RSAES-OAEP encoding algorithm.
3. Verify that at least 40 bytes of the data was decrypted.
4. Verify that the random number that is contained in the first 16 bytes of the data that was decrypted matches the random number that the display miniport driver's [**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md) returned when the handle in the **ProtectedOutputHandle** parameter was passed to it.
5. Cache the 128-bit AES signing key and the two 32-bit sequence numbers.

Before a protected output object's handle is passed to **DxgkDdiOPMSetSigningKeyAndSequenceNumbers**, it is passed to [**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md). Each protected output object handle is only passed to **DxgkDdiOPMSetSigningKeyAndSequenceNumbers** once.

**DxgkDdiOPMSetSigningKeyAndSequenceNumbers** should be made pageable.

### RSAES-OAEP and MGF1 Parameters

RSAES-OAEP is a parameterized encryption scheme and MGF1 is a parameterized mask generation function. Following are the parameters OPM uses when it uses RSAES-OAEP and MGF1. For more information about the following terms and the RSA Cryptography Standard, see the [RSA Laboratories](https://www.rsa.com/) and [Secure Hashing](https://csrc.nist.gov/projects/hash-functions) websites.

## -see-also

[**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md)

[**DxgkDdiOPMCreateProtectedOutput**](nc-dispmprt-dxgkddi_opm_create_protected_output.md)

[**DXGKMDT_OPM_ENCRYPTED_PARAMETERS**](..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_encrypted_parameters.md)

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md)

[**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md)

[**DxgkDdiOPMConfigureProtectedOutput**](nc-dispmprt-dxgkddi_opm_configure_protected_output.md)

