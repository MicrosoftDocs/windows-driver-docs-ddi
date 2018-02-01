---
UID: NS:ntddk._BDCB_IMAGE_INFORMATION
title: "_BDCB_IMAGE_INFORMATION"
author: windows-driver-content
description: The BDCB_IMAGE_INFORMATION structure describes information about a boot-start driver that is about to be initialized, provided by Windows to a boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\bdcb_image_information.htm
old-project: kernel
ms.assetid: 9D0A4D67-3284-4BCC-AC81-F0BCCC2DB9B7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PBDCB_IMAGE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], kernel.bdcb_image_information, BDCB_IMAGE_INFORMATION structure [Kernel-Mode Driver Architecture], ntddk/PBDCB_IMAGE_INFORMATION, *PBDCB_IMAGE_INFORMATION, PBDCB_IMAGE_INFORMATION, ntddk/BDCB_IMAGE_INFORMATION, _BDCB_IMAGE_INFORMATION, BDCB_IMAGE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	BDCB_IMAGE_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PBDCB_IMAGE_INFORMATION, BDCB_IMAGE_INFORMATION"
---

# _BDCB_IMAGE_INFORMATION structure


## -description


The <b>BDCB_IMAGE_INFORMATION</b> structure describes information about a boot-start driver that is about to 
    be initialized, provided by Windows to a boot-start driver's 
    <a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a> routine.


## -syntax


````
typedef struct _BDCB_IMAGE_INFORMATION {
  BDCB_CLASSIFICATION Classification;
  ULONG               ImageFlags;
  UNICODE_STRING      ImageName;
  UNICODE_STRING      RegistryPath;
  UNICODE_STRING      CertificatePublisher;
  UNICODE_STRING      CertificateIssuer;
  PVOID               ImageHash;
  PVOID               CertificateThumbprint;
  ULONG               ImageHashAlgorithm;
  ULONG               ThumbprintHashAlgorithm;
  ULONG               ImageHashLength;
  ULONG               CertificateThumbprintLength;
} BDCB_IMAGE_INFORMATION, *PBDCB_IMAGE_INFORMATION;
````


## -struct-fields




### -field Classification

The classification of the boot start image.


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
The boot start image failed code integrity but load was allowed because of boot policy (code integrity not required on the platform, or code integrity disabled because of boot setting,  debugging, or both).

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

<a href="..\ntddk\ne-ntddk-_bdcb_classification.md">BDCB_CLASSIFICATION</a>

<a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BDCB_IMAGE_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

