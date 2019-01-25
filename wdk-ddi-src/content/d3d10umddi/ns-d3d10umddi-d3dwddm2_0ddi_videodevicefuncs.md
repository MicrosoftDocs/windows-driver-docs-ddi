---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEODEVICEFUNCS
title: D3DWDDM2_0DDI_VIDEODEVICEFUNCS (d3d10umddi.h)
description: Specifies the video function table for the Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.0 and later drivers.
old-location: display\d3dwddm2_0ddi_videodevicefuncs.htm
ms.assetid: 59D06B73-413B-4595-841E-7E0A696A3AC2
ms.date: 05/10/2018
ms.keywords: D3DWDDM2_0DDI_VIDEODEVICEFUNCS, D3DWDDM2_0DDI_VIDEODEVICEFUNCS structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEODEVICEFUNCS, display.d3dwddm2_0ddi_videodevicefuncs
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_VIDEODEVICEFUNCS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEODEVICEFUNCS
---

# D3DWDDM2_0DDI_VIDEODEVICEFUNCS structure


## -description


Specifies the video function table for the  Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.0 and later drivers.


## -struct-fields




### -field pfnGetVideoDecoderProfileCount

The entry point for the driver's <a href="https://msdn.microsoft.com/ae24bc29-177e-48a1-adf9-ed8c79b7f39c">VideoDecoderProfileCount</a> function.


### -field pfnGetVideoDecoderProfile

The entry point for the driver's <a href="https://msdn.microsoft.com/75576152-0afd-4602-b481-bf1d6d9348b3">VideoDecoderProfile</a> function.


### -field pfnCheckVideoDecoderFormat

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451615">CheckVideoDecoderFormat</a> function.


### -field pfnGetVideoDecoderConfigCount

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451665">GetVideoDecoderConfig</a> function.


### -field pfnGetVideoDecoderConfig

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451665">GetVideoDecoderConfig</a> function.


### -field pfnGetVideoDecoderBufferTypeCount

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451663">GetVideoDecoderBufferTypeCount</a> function.


### -field pfnGetVideoDecoderBufferInfo

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451661">GetVideoDecoderBufferInfo</a> function.


### -field pfnCalcPrivateVideoDecoderSize

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451610">CalcPrivateVideoDecoderSize</a> function.


### -field pfnCreateVideoDecoder

The entry point for the driver's <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.


### -field pfnDestroyVideoDecoder

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451634">DestroyVideoDecoder</a> function.


### -field pfnVideoDecoderExtension

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451699">VideoDecoderExtension</a> function.


### -field pfnVideoDecoderBeginFrame

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a> function.


### -field pfnVideoDecoderEndFrame

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451698">VideoDecoderEndFrame</a> function.


### -field pfnVideoDecoderSubmitBuffers

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451701">VideoDecoderSubmitBuffers</a> function.


### -field pfnCalcPrivateVideoProcessorEnumSize

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451611">CalcPrivateVideoProcessorEnumSize</a> function.


### -field pfnCreateVideoProcessorEnum

The entry point for the driver's <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a> function.


### -field pfnDestroyVideoProcessorEnum

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451639">DestroyVideoProcessorEnum</a> function.


### -field pfnCheckVideoProcessorFormat

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451616">CheckVideoProcessorFormat</a> function.


### -field pfnGetVideoProcessorCaps

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function.


### -field pfnGetVideoProcessorRateConversionCaps

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451690">GetVideoProcessorRateConversionCaps</a> function.


### -field pfnGetVideoProcessorCustomRate

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451676">GetVideoProcessorCustomRate</a> function.


### -field pfnGetVideoProcessorFilterRange

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451689">GetVideoProcessorFilterRange</a> function.


### -field pfnCalcPrivateVideoProcessorSize

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451614">CalcPrivateVideoProcessorSize</a> function.


### -field pfnCreateVideoProcessor

The entry point for the driver's <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.


### -field pfnDestroyVideoProcessor

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451638">DestroyVideoProcessor</a> function.


### -field pfnVideoProcessorSetOutputTargetRect

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439790">VideoProcessorSetOutputTargetRect</a> function.


### -field pfnVideoProcessorSetOutputBackgroundColor

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn459003">VideoProcessorSetOutputBackgroundColor</a> function.


### -field pfnVideoProcessorSetOutputColorSpace

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439782">VideoProcessorSetOutputColorSpace</a> function.


### -field pfnVideoProcessorSetOutputAlphaFillMode

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439778">VideoProcessorSetOutputAlphaFillMode</a> function.


### -field pfnVideoProcessorSetOutputConstriction

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439784">VideoProcessorSetOutputConstriction</a> function.


### -field pfnVideoProcessorSetOutputStereoMode

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439788">VideoProcessorSetOutputStereoMode</a> function.


### -field pfnVideoProcessorSetOutputExtension

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439786">VideoProcessorSetOutputExtension</a> function.


### -field pfnVideoProcessorGetOutputExtension

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451705">VideoProcessorGetOutputExtension</a> function.


### -field pfnVideoProcessorSetStreamFrameFormat

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439804">VideoProcessorSetStreamFrameFormat</a> function.


### -field pfnVideoProcessorSetStreamColorSpace

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439796">VideoProcessorSetStreamColorSpace</a> function.


### -field pfnVideoProcessorSetStreamOutputRate

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439807">VideoProcessorSetStreamOutputRate</a> function.


### -field pfnVideoProcessorSetStreamSourceRect

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439815">VideoProcessorSetStreamSourceRect</a> function.


### -field pfnVideoProcessorSetStreamDestRect

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn459004">VideoProcessorSetStreamDestRect</a> function.


### -field pfnVideoProcessorSetStreamAlpha

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439792">VideoProcessorSetStreamAlpha</a> function.


### -field pfnVideoProcessorSetStreamPalette

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439809">VideoProcessorSetStreamPalette</a> function.


### -field pfnVideoProcessorSetStreamPixelAspectRatio

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439811">VideoProcessorSetStreamPixelAspectRatio</a> function.


### -field pfnVideoProcessorSetStreamLumaKey

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439805">VideoProcessorSetStreamLumaKey</a> function.


### -field pfnVideoProcessorSetStreamStereoFormat

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439817">VideoProcessorSetStreamStereoFormat</a> function.


### -field pfnVideoProcessorSetStreamAutoProcessingMode

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439794">VideoProcessorSetStreamAutoProcessingMode</a> function.


### -field pfnVideoProcessorSetStreamFilter

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439802">VideoProcessorSetStreamFilter</a> function.


### -field pfnVideoProcessorSetStreamExtension

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439800">VideoProcessorSetStreamExtension</a> function.


### -field pfnVideoProcessorGetStreamExtension

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439773">VideoProcessorGetStreamExtension</a> function.


### -field pfnVideoProcessorBlt

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451703">VideoProcessorBlt</a> function.


### -field pfnCalcPrivateVideoDecoderOutputViewSize

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451608">CalcPrivateVideoDecoderOutputViewSize</a> function.


### -field pfnCreateVideoDecoderOutputView

The entry point for the driver's <a href="https://msdn.microsoft.com/a5a32b4e-799c-4d18-995d-f804e6dff85c">CreateVideoDecoderOutputView</a> function.


### -field pfnDestroyVideoDecoderOutputView

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451636">DestroyVideoDecoderOutputView</a> function.


### -field pfnCalcPrivateVideoProcessorInputViewSize

The entry point for the driver's <a href="https://msdn.microsoft.com/3cdf467c-41f5-4a44-b10a-41aeb76ca815">CalcPrivateVideoProcessorInputViewSize</a> function.


### -field pfnCreateVideoProcessorInputView

The entry point for the driver's <a href="https://msdn.microsoft.com/f3942c53-e366-41c5-9f43-d093fa6b6ed6">CreateVideoProcessorInputView</a> function.


### -field pfnDestroyVideoProcessorInputView

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451642">DestroyVideoProcessorInputView</a> function.


### -field pfnCalcPrivateVideoProcessorOutputViewSize

The entry point for the driver's <a href="https://msdn.microsoft.com/2cf09e91-e83b-47ae-bf34-037dc01d7e80">CalcPrivateVideoProcessorOutputViewSize</a> function.


### -field pfnCreateVideoProcessorOutputView

The entry point for the driver's <a href="https://msdn.microsoft.com/619695dc-8525-4200-a0c2-8ce0fb1010ed">CreateVideoProcessorOutputView</a> function.


### -field pfnDestroyVideoProcessorOutputView

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451644">DestroyVideoProcessorOutputView</a> function.


### -field pfnVideoProcessorInputViewReadAfterWriteHazard

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439775">VideoProcessorInputViewReadAfterWriteHazard</a> function.


### -field pfnGetContentProtectionCaps

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451656">GetContentProtectionCaps</a> function.


### -field pfnGetCryptoKeyExchangeType

The entry point for the driver's <a href="https://msdn.microsoft.com/64870c9f-facf-4344-93d0-12cbcec86e11">GetCryptoKeyExchangeType</a> function.


### -field pfnCalcPrivateCryptoSessionSize

The entry point for the driver's <a href="https://msdn.microsoft.com/9ca0fdd5-a724-4d5d-81b2-8885b2aed1ca">CalcPrivateCryptoSessionSize</a> function.


### -field pfnCreateCryptoSession

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.


### -field pfnDestroyCryptoSession

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451632">DestroyCryptoSession</a> function.


### -field pfnGetCertificateSize

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451654">GetCertificateSize</a> function.


### -field pfnGetCertificate

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451652">GetCertificate</a> function.


### -field pfnNegotiateCryptoSessionKeyExchange

The entry point for the driver's <a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a> function.


### -field pfnEncryptionBlt

The entry point for the driver's <a href="https://msdn.microsoft.com/ea6f1b8c-d65a-4d6d-a7ae-998374bf5bfb">EncryptionBlt(D3D11_1)</a> function.


### -field pfnDecryptionBlt

The entry point for the driver's <a href="https://msdn.microsoft.com/36aeb826-251e-404e-8ce3-6b2246ff07bc">DecryptionBlt(D3D11_1)</a> function.


### -field pfnStartSessionKeyRefresh

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451696">StartSessionKeyRefresh</a> function.


### -field pfnFinishSessionKeyRefresh

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451648">FinishSessionKeyRefresh</a> function.


### -field pfnGetEncryptionBltKey

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451660">GetEncryptionBltKey</a> function.


### -field pfnCalcPrivateAuthenticatedChannelSize

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451604">CalcPrivateAuthenticatedChannelSize</a> function.


### -field pfnCreateAuthenticatedChannel

The entry point for the driver's <a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a> function.


### -field pfnDestroyAuthenticatedChannel

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451630">DestroyAuthenticatedChannel</a> function.


### -field pfnNegotiateAuthenticatedChannelKeyExchange

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451691">NegotiateAuthenticatedChannelKeyExchange</a> function.


### -field pfnQueryAuthenticatedChannel

The entry point for the driver's <a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a> function.


### -field pfnConfigureAuthenticatedChannel

The entry point for the driver's <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function.


### -field pfnVideoDecoderGetHandle

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451700">VideoDecoderGetHandle</a> function.


### -field pfnCryptoSessionGetHandle

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451626">CryptoSessionGetHandle</a> function.


### -field pfnVideoProcessorSetStreamRotation

The entry point for the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439813">VideoProcessorSetStreamRotation</a> function.


### -field pfnGetCaptureHandle

The entry point for the driver's <a href="https://msdn.microsoft.com/b1ca7cf0-fe63-452f-8360-fdba05875719">GetCaptureHandle</a> function.


### -field pfnGetDataForNewHardwareKey

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906350">GetDataForNewHardwareKey</a> function.


### -field pfnCheckCryptoSessionStatus

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906316">CheckCryptoSessionStatus</a> function.


### -field pfnVideoDecoderSubmitBuffers1

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906377">VideoDecoderSubmitBuffers1</a> function.


### -field pfnQueryVideoCapabilities

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906368">QueryVideoCapabilities</a> function.


### -field pfnCheckVideoProcessorFormatConversion

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906317">CheckVideoProcessorFormatConversion</a> function.


### -field pfnVideoDecoderEnableDownsampling

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906376">VideoDecoderEnableDownsampling</a> function.


### -field pfnVideoDecoderUpdateDownsampling

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906378">VideoDecoderUpdateDownsampling</a> function.


### -field pfnVideoProcessorSetStreamMirror

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906383">VideoProcessorSetStreamMirror</a> function.


### -field pfnVideoProcessorSetOutputColorSpace1

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906380">VideoProcessorSetOutputColorSpace1</a> function.


### -field pfnVideoProcessorSetStreamColorSpace1

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906382">VideoProcessorSetStreamColorSpace1</a> function.


### -field pfnVideoProcessorSetOutputShaderUsage

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906381">VideoProcessorSetOutputShaderUsage</a> function.


### -field pfnVideoProcessorGetBehaviorHints

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906379">VideoProcessorGetBehaviorHints</a> function.


### -field pfnGetCryptoSessionPrivateDataSize

The entry point for the driver's     <a href="https://msdn.microsoft.com/library/windows/hardware/dn906349">GetCryptoSessionPrivateDataSize</a> function.

