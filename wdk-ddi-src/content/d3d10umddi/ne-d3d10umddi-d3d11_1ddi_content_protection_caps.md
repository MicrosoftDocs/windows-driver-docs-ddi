---
UID: NE:d3d10umddi.D3D11_1DDI_CONTENT_PROTECTION_CAPS
title: D3D11_1DDI_CONTENT_PROTECTION_CAPS
author: windows-driver-content
description: Describes content-protection capabilities.
old-location: display\d3d11_1ddi_content_protection_caps.htm
old-project: display
ms.assetid: de2d5e08-1c8f-4c67-91e0-db7552b0b883
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_PROTECTION_ALWAYS_ON, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPT_SLICEDATA_ONLY, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_HARDWARE, D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPT_SLICEDATA_ONLY, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT, D3D11_1DDI_CONTENT_PROTECTION_CAPS enumeration [Display Devices], D3D11_1DDI_CONTENT_PROTECTION_CAPS_PROTECTION_ALWAYS_ON, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK, d3d10umddi/D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_TRANSITION, D3D11_1DDI_CONTENT_PROTECTION_CAPS_SOFTWARE, D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECT_UNCOMPRESSED, d3d10umddi/D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_TEARDOWN, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_PARTIAL_DECRYPTION, D3D11_1DDI_CONTENT_PROTECTION_CAPS_PARTIAL_DECRYPTION, D3D11_1DDI_CONTENT_PROTECTION_CAPS_SEQUENTIAL_CTR_IV, D3D11_1DDI_CONTENT_PROTECTION_CAPS_FRESHEN_SESSION_KEY, D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_FRESHEN_SESSION_KEY, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS, D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT, d3d10umddi/D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_PAGEABLE, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_CONTENT_KEY, D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_TEARDOWN, D3D11_1DDI_CONTENT_PROTECTION_CAPS_HARDWARE, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_SOFTWARE, display.d3d11_1ddi_content_protection_caps, D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_DRM_COMMUNICATION, d3d10umddi/D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_DRM_COMMUNICATION, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_SEQUENTIAL_CTR_IV, D3D11_1DDI_CONTENT_PROTECTION_CAPS, d3d10umddi/D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECT_UNCOMPRESSED, D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_PAGEABLE, d3d10umddi/D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK_KEY, D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_TRANSITION, d3d10umddi/, D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK_KEY, D3D11_1DDI_CONTENT_PROTECTION_CAPS_CONTENT_KEY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D11_1DDI_CONTENT_PROTECTION_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_CONTENT_PROTECTION_CAPS
---

# D3D11_1DDI_CONTENT_PROTECTION_CAPS enumeration


## -description


Describes content-protection capabilities.


## -syntax


````
typedef enum D3D11_1DDI_CONTENT_PROTECTION_CAPS { 
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_SOFTWARE                                 = 0x00000001,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_HARDWARE                                 = 0x00000002,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_PROTECTION_ALWAYS_ON                     = 0x00000004,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_PARTIAL_DECRYPTION                       = 0x00000008,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_CONTENT_KEY                              = 0x00000010,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_FRESHEN_SESSION_KEY                      = 0x00000020,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK                      = 0x00000040,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK_KEY                  = 0x00000080,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_SEQUENTIAL_CTR_IV                        = 0x00000100,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPT_SLICEDATA_ONLY                   = 0x00000200,
  D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT                           = 0x00000400,
#if D3D11DDI_MINOR_HEADER_VERSION >= 5
  D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECT_UNCOMPRESSED         = 0x00000800,
  D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_PAGEABLE    = 0x00001000,
  D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_TRANSITION  = 0x00002000,
  D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_TEARDOWN                     = 0x00004000,
  D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_DRM_COMMUNICATION            = 0x00008000,
#endif 
  
} D3D11_1DDI_CONTENT_PROTECTION_CAPS;
````


## -enum-fields




### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_SOFTWARE

The encryption is implemented in software by the driver.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_HARDWARE

The encryption is implemented in hardware by the GPU.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_PROTECTION_ALWAYS_ON

Content protection is always applied to a protected surface, regardless of whether the application explicitly enables protection.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_PARTIAL_DECRYPTION

The driver can use partially encrypted buffers. If this capability is not present, the entire buffer must be either encrypted or clear.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_CONTENT_KEY

The driver can encrypt data using a separate content key that is encrypted using the session key.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_FRESHEN_SESSION_KEY

The driver can refresh the session key without renegotiating the key.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK

The driver can read back encrypted data from a protected surface. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a>.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPTED_READ_BACK_KEY

The driver requires a separate key to read encrypted data from a protected surface.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_SEQUENTIAL_CTR_IV

If the encryption type is <b>D3D11_1DDI_CRYPTO_TYPE_AES128_CTR</b>, the application must use a sequential count in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a> structure. For more information, see the Remarks for the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a> function.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_ENCRYPT_SLICEDATA_ONLY

The driver supports encrypted slice data, but does not support any other encrypted data in the DirectX Video Accelerator (DXVA) 2 compressed buffer. The caller should not encrypt any data within the buffer other than the slice data.


### -field D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT

The driver supports calls to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt.md">DecryptionBlt(D3D11_1)</a> function.


### -field D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECT_UNCOMPRESSED

The hardware supports the protection of specific resources using the WDDM 2.0 and later versions of the Graphics Content Protection DDI. This protection means:
<ul>
<li>The contents of a protected allocation can never be read by the CPU.</li>
<li>The hardware can ensure that a protected resource cannot be copied to an unprotected resource.</li>
</ul>Supported starting with Windows 10.


### -field D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_PAGEABLE

The physical pages of a protected resource can be evicted and potentially paged to disk in low memory conditions without losing the contents of the resource when paged back in.

Supported starting with Windows 10.


### -field D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_PROTECTED_MEMORY_TRANSITION

The hardware or driver can transition allocations between protected and unprotected states by calling <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_sethardwareprotection.md">SetHardwareProtection</a>  without requiring the allocation to be re-created.

Supported starting with Windows 10.


### -field D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_TEARDOWN

The hardware supports an automatic tear-down mechanism that could trigger hardware keys or protected content to become lost in some conditions.  The application can register to know when these events occur.

Supported starting with Windows 10.


### -field D3DWDDM2_0DDI_CONTENT_PROTECTION_CAPS_HARDWARE_DRM_COMMUNICATION

The secure environment is tightly coupled with the GPU and an <b>ID3D11CryptoSession</b> should be used for communication between the user mode DRM component and the secure execution environment.

Supported starting with Windows 10.





## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt.md">DecryptionBlt(D3D11_1)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_sethardwareprotection.md">SetHardwareProtection</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_CONTENT_PROTECTION_CAPS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

