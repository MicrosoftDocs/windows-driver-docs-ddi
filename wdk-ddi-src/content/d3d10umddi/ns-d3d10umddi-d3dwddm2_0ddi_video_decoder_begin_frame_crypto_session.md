---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
title: D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION is used along with CreateCryptoSession to perform crypto operations into and out of protected memory.
old-location: display\d3d11_video_decoder_begin_frame_crypto_session.htm
old-project: display
ms.assetid: EC08022F-319E-4E49-A003-B98EEADAA0CC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION, D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION, display.d3d11_video_decoder_begin_frame_crypto_session, D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION, D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure [Display Devices], D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION
---

# D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION</b> is used along with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> to   perform crypto operations into and out of protected memory.


## -syntax


````
typedef struct D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION {
  D3D11_1DDI_HCRYPTOSESSION              hCryptoSession;
  _Field_size_opt_(BlobSize) void        *pBlob;
  UINT                                   BlobSize;
  GUID                                   *pKeyInfoId;
  _Field_size_opt_(PrivateDataSize) void *pPrivateData;
  UINT                                   PrivateDataSize;
} D3D11_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION;
````


## -struct-fields




### -field hCryptoSession

A handle to a cryptographic session object created using <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>. 


### -field pBlob

A pointer to an IHV-defined blob allocated by an upstream DRM component.  The blob identifies the sealed decryption key to be used for the current frame.


### -field BlobSize

Size of the IHV-defined blob referenced in the <b>pBlob</b> member.


### -field pKeyInfoId

A pointer to a <b>GUID</b> identifying the hardware key.


### -field pPrivateData

The definition of this buffer is dependent on the implementation of the secure environment. It may contain data specific to the current frame.


### -field PrivateDataSize

Contains the size of the memory buffer referenced by the <b>pPrivateData</b> member.


## -remarks



A pointer to this structure is passed in the <b>pContentKey</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_videodecoderbeginframe.md">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a> structure when <b>D3DWDDM2_0DDI_DECODER_ENCRYPTION_HW_CENC</b> is specified in the <b>guidConfigBitstreamEncryption</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure when creating the video decoder object.






## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_videodecoderbeginframe.md">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

