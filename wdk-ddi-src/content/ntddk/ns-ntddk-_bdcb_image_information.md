---
UID: NS:ntddk._BDCB_IMAGE_INFORMATION
title: _BDCB_IMAGE_INFORMATION (ntddk.h)
description: The BDCB_IMAGE_INFORMATION structure describes information about a boot-start driver that is about to be initialized, provided by Windows to a boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\bdcb_image_information.htm
tech.root: kernel
ms.assetid: 9D0A4D67-3284-4BCC-AC81-F0BCCC2DB9B7
ms.date: 04/30/2018
ms.keywords: "*PBDCB_IMAGE_INFORMATION, BDCB_IMAGE_INFORMATION, BDCB_IMAGE_INFORMATION structure [Kernel-Mode Driver Architecture], PBDCB_IMAGE_INFORMATION, PBDCB_IMAGE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _BDCB_IMAGE_INFORMATION, kernel.bdcb_image_information, ntddk/BDCB_IMAGE_INFORMATION, ntddk/PBDCB_IMAGE_INFORMATION"
ms.topic: struct
f1_keywords:
 - "ntddk/BDCB_IMAGE_INFORMATION"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
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
- ntddk.h
api_name:
- BDCB_IMAGE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: BDCB_IMAGE_INFORMATION, *PBDCB_IMAGE_INFORMATION
---

# _BDCB_IMAGE_INFORMATION structure


## -description


The <b>BDCB_IMAGE_INFORMATION</b> structure describes information about a boot-start driver that is about to 
    be initialized, provided by Windows to a boot-start driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-boot_driver_callback_function">BOOT_DRIVER_CALLBACK_FUNCTION</a> routine.


## -struct-fields




### -field Classification

An enumeration of type [**BDCB_CLASSIFICATION**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_bdcb_classification) that the ELAM driver sets to specify the classification of the boot start image.


### -field ImageFlags

Bit flags that describe the image. The following values are defined.
      

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
Bit 0

</td>
<td>
The boot start image is a dependent DLL.

</td>
</tr>
<tr>
<td>
Bit 1

</td>
<td>
The boot start image failed code integrity but load was allowed because of boot policy (code integrity not required on the platform, or code integrity disabled because of boot setting,  debugging, or both).  The symbolic name for bit 1 is `BDCB_IMAGEFLAGS_FAILED_CODE_INTEGRITY.`

</td>
</tr>
<tr>
<td>
Bits 2-31

</td>
<td>
Do not use. Reserved.

</td>
</tr>
</table>
 


### -field ImageName

The name of the boot-start driver's binary image.


### -field RegistryPath

The path in the registry where the boot-start driver is registered.


### -field CertificatePublisher

The publisher of the image's certificate. If the image is not signed, the string is empty ("").


### -field CertificateIssuer

The issuer of the image's certificate. If the image is not signed, the string is empty ("").


### -field ImageHash

The Authenticode hash of the image, which can be calculated by  using SignTool.exe (Sign Tool). 


### -field CertificateThumbprint

The hash of the certificate of the signer to be signed. Run <b>certutil –dump x,cer</b> to view this value as  "Signature Hash".


### -field ImageHashAlgorithm

The algorithm of the image hash. The following values are listed for reference.
      

<table>
<tr>
<th>Value</th>
</tr>
<tr>
<td>
ALG_CLASS_HASH

</td>
</tr>
<tr>
<td>
ALG_CLASS_ANY

</td>
</tr>
<tr>
<td>
ALG_SID_MD5

</td>
</tr>
<tr>
<td>
ALG_SID_SHA1

</td>
</tr>
<tr>
<td>
ALG_SID_SHA_256

</td>
</tr>
<tr>
<td>
ALG_SID_SHA_384

</td>
</tr>
<tr>
<td>
ALG_SID_SHA_512

</td>
</tr>
<tr>
<td>
CALG_MD5

</td>
</tr>
<tr>
<td>
CALG_SHA1

</td>
</tr>
<tr>
<td>
CALG_SHA_256

</td>
</tr>
<tr>
<td>
CALG_SHA_384

</td>
</tr>
<tr>
<td>
CALG_SHA_512

</td>
</tr>
</table>
 


### -field ThumbprintHashAlgorithm

The algorithm of the certificate thumbprint. This member should be ignored if <b>CertificateThumbprint</b> is NULL.


### -field ImageHashLength

The length of data pointed to by the <b>ImageHash</b> member.


### -field CertificateThumbprintLength

The length of data pointed to by the <b>CertificateThumbprint</b> member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_bdcb_classification">BDCB_CLASSIFICATION</a>



[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)

[**ALG_ID**](https://docs.microsoft.com/windows/desktop/SecCrypto/alg-id)

