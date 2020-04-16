---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0
title: D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0 (d3d10umddi.h)
description: Specifies the video function table for the Microsoft Direct3D driver device object.
ms.assetid: 1cc34376-1bc6-471c-8d4b-6d7fed0488a5
ms.date: 10/19/2018
keywords: ["D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0 structure"]
f1_keywords:
 - "d3d10umddi/D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0"
ms.keywords: D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0, D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0,
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0 structure

## -description

Specifies the video function table for the Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.4 and later drivers.

>**Note** The driver must support WDDM 2.4 version of the user mode DDI.

## -struct-fields

### -field pfnGetVideoDecoderProfileCount

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount.md">VideoDecoderProfileCount</a> function.

### -field pfnGetVideoDecoderProfile

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofile.md">VideoDecoderProfile</a> function.

### -field pfnCheckVideoDecoderFormat

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkvideodecoderformat.md">CheckVideoDecoderFormat</a> function.

### -field pfnGetVideoDecoderConfigCount

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount.md">GetVideoDecoderConfig</a> function.

### -field pfnGetVideoDecoderConfig

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfig.md">GetVideoDecoderConfig</a> function.

### -field pfnGetVideoDecoderBufferTypeCount

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbuffertypecount.md">GetVideoDecoderBufferTypeCount</a> function.

### -field pfnGetVideoDecoderBufferInfo

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbufferinfo.md">GetVideoDecoderBufferInfo</a> function.

### -field pfnCalcPrivateVideoDecoderSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md">CalcPrivateVideoDecoderSize</a> function.

### -field pfnCreateVideoDecoder

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a> function.

### -field pfnDestroyVideoDecoder

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoder.md">DestroyVideoDecoder</a> function.

### -field pfnVideoDecoderExtension

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderextension.md">VideoDecoderExtension</a> function.

### -field pfnVideoDecoderBeginFrame

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a> function.

### -field pfnVideoDecoderEndFrame

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderendframe.md">VideoDecoderEndFrame</a> function.

### -field pfnVideoDecoderSubmitBuffers

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers.md">VideoDecoderSubmitBuffers</a> function.

### -field pfnCalcPrivateVideoProcessorEnumSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorenumsize.md">CalcPrivateVideoProcessorEnumSize</a> function.

### -field pfnCreateVideoProcessorEnum

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a> function.

### -field pfnDestroyVideoProcessorEnum

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorenum.md">DestroyVideoProcessorEnum</a> function.

### -field pfnCheckVideoProcessorFormat

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkvideoprocessorformat.md">CheckVideoProcessorFormat</a> function.

### -field pfnGetVideoProcessorCaps

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function.

### -field pfnGetVideoProcessorRateConversionCaps

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a> function.

### -field pfnGetVideoProcessorCustomRate

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md">GetVideoProcessorCustomRate</a> function.

### -field pfnGetVideoProcessorFilterRange

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorfilterrange.md">GetVideoProcessorFilterRange</a> function.

### -field pfnCalcPrivateVideoProcessorSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize.md">CalcPrivateVideoProcessorSize</a> function.

### -field pfnCreateVideoProcessor

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function.

### -field pfnDestroyVideoProcessor

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessor.md">DestroyVideoProcessor</a> function.

### -field pfnVideoProcessorSetOutputTargetRect

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputtargetrect.md">VideoProcessorSetOutputTargetRect</a> function.

### -field pfnVideoProcessorSetOutputBackgroundColor

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor.md">VideoProcessorSetOutputBackgroundColor</a> function.

### -field pfnVideoProcessorSetOutputColorSpace

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputcolorspace.md">VideoProcessorSetOutputColorSpace</a> function.

### -field pfnVideoProcessorSetOutputAlphaFillMode

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a> function.

### -field pfnVideoProcessorSetOutputConstriction

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md">VideoProcessorSetOutputConstriction</a> function.

### -field pfnVideoProcessorSetOutputStereoMode

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode.md">VideoProcessorSetOutputStereoMode</a> function.

### -field pfnVideoProcessorSetOutputExtension

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputextension.md">VideoProcessorSetOutputExtension</a> function.

### -field pfnVideoProcessorGetOutputExtension

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetoutputextension.md">VideoProcessorGetOutputExtension</a> function.

### -field pfnVideoProcessorSetStreamFrameFormat

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamframeformat.md">VideoProcessorSetStreamFrameFormat</a> function.

### -field pfnVideoProcessorSetStreamColorSpace

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamcolorspace.md">VideoProcessorSetStreamColorSpace</a> function.

### -field pfnVideoProcessorSetStreamOutputRate

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamoutputrate.md">VideoProcessorSetStreamOutputRate</a> function.

### -field pfnVideoProcessorSetStreamSourceRect

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamsourcerect.md">VideoProcessorSetStreamSourceRect</a> function.

### -field pfnVideoProcessorSetStreamDestRect

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamdestrect.md">VideoProcessorSetStreamDestRect</a> function.

### -field pfnVideoProcessorSetStreamAlpha

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamalpha.md">VideoProcessorSetStreamAlpha</a> function.

### -field pfnVideoProcessorSetStreamPalette

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampalette.md">VideoProcessorSetStreamPalette</a> function.

### -field pfnVideoProcessorSetStreamPixelAspectRatio

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampixelaspectratio.md">VideoProcessorSetStreamPixelAspectRatio</a> function.

### -field pfnVideoProcessorSetStreamLumaKey

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md">VideoProcessorSetStreamLumaKey</a> function.

### -field pfnVideoProcessorSetStreamStereoFormat

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a> function.

### -field pfnVideoProcessorSetStreamAutoProcessingMode

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamautoprocessingmode.md">VideoProcessorSetStreamAutoProcessingMode</a> function.

### -field pfnVideoProcessorSetStreamFilter

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamfilter.md">VideoProcessorSetStreamFilter</a> function.

### -field pfnVideoProcessorSetStreamExtension

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamextension.md">VideoProcessorSetStreamExtension</a> function.

### -field pfnVideoProcessorGetStreamExtension

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetstreamextension.md">VideoProcessorGetStreamExtension</a> function.

### -field pfnVideoProcessorBlt

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a> function.

### -field pfnCalcPrivateVideoDecoderOutputViewSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecoderoutputviewsize.md">CalcPrivateVideoDecoderOutputViewSize</a> function.

### -field pfnCreateVideoDecoderOutputView

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a> function.

### -field pfnDestroyVideoDecoderOutputView

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoderoutputview.md">DestroyVideoDecoderOutputView</a> function.

### -field pfnCalcPrivateVideoProcessorInputViewSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorinputviewsize.md">CalcPrivateVideoProcessorInputViewSize</a> function.

### -field pfnCreateVideoProcessorInputView

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a> function.

### -field pfnDestroyVideoProcessorInputView

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorinputview.md">DestroyVideoProcessorInputView</a> function.

### -field pfnCalcPrivateVideoProcessorOutputViewSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a> function.

### -field pfnCreateVideoProcessorOutputView

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessoroutputview.md">CreateVideoProcessorOutputView</a> function.

### -field pfnDestroyVideoProcessorOutputView

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessoroutputview.md">DestroyVideoProcessorOutputView</a> function.

### -field pfnVideoProcessorInputViewReadAfterWriteHazard

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorinputviewreadafterwritehazard.md">VideoProcessorInputViewReadAfterWriteHazard</a> function.

### -field pfnGetContentProtectionCaps

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcontentprotectioncaps.md">GetContentProtectionCaps</a> function.

### -field pfnGetCryptoKeyExchangeType

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype.md">GetCryptoKeyExchangeType</a> function.

### -field pfnCalcPrivateCryptoSessionSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize.md">CalcPrivateCryptoSessionSize</a> function.

### -field pfnCreateCryptoSession

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.

### -field pfnDestroyCryptoSession

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroycryptosession.md">DestroyCryptoSession</a> function.

### -field pfnGetCertificateSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a> function.

### -field pfnGetCertificate

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a> function.

### -field pfnNegotiateCryptoSessionKeyExchange

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a> function.

### -field pfnEncryptionBlt

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a> function.

### -field pfnDecryptionBlt

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt.md">DecryptionBlt(D3D11_1)</a> function.

### -field pfnStartSessionKeyRefresh

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a> function.

### -field pfnFinishSessionKeyRefresh

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function.

### -field pfnGetEncryptionBltKey

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey.md">GetEncryptionBltKey</a> function.

### -field pfnCalcPrivateAuthenticatedChannelSize

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateauthenticatedchannelsize.md">CalcPrivateAuthenticatedChannelSize</a> function.

### -field pfnCreateAuthenticatedChannel

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.

### -field pfnDestroyAuthenticatedChannel

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a> function.

### -field pfnNegotiateAuthenticatedChannelKeyExchange

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiateauthenticatedchannelkeyexchange.md">NegotiateAuthenticatedChannelKeyExchange</a> function.

### -field pfnQueryAuthenticatedChannel

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> function.

### -field pfnConfigureAuthenticatedChannel

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.

### -field pfnVideoDecoderGetHandle

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecodergethandle.md">VideoDecoderGetHandle</a> function.

### -field pfnCryptoSessionGetHandle

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_cryptosessiongethandle.md">CryptoSessionGetHandle</a> function.

### -field pfnVideoProcessorSetStreamRotation

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamrotation.md">VideoProcessorSetStreamRotation</a> function.

### -field pfnGetCaptureHandle

The entry point for the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a> function.

### -field pfnGetDataForNewHardwareKey

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getdatafornewhardwarekey.md">GetDataForNewHardwareKey</a> function.

### -field pfnCheckCryptoSessionStatus

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_checkcryptosessionstatus.md">CheckCryptoSessionStatus</a> function.

### -field pfnVideoDecoderSubmitBuffers2

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecodersubmitbuffers1.md">VideoDecoderSubmitBuffers1</a> function.

### -field pfnQueryVideoCapabilities

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md">QueryVideoCapabilities</a> function.

### -field pfnCheckVideoProcessorFormatConversion

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion.md">CheckVideoProcessorFormatConversion</a> function.

### -field pfnVideoDecoderEnableDownsampling

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling.md">VideoDecoderEnableDownsampling</a> function.

### -field pfnVideoDecoderUpdateDownsampling

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderupdatedownsampling.md">VideoDecoderUpdateDownsampling</a> function.

### -field pfnVideoProcessorSetStreamMirror

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md">VideoProcessorSetStreamMirror</a> function.

### -field pfnVideoProcessorSetOutputColorSpace1

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputcolorspace1.md">VideoProcessorSetOutputColorSpace1</a> function.

### -field pfnVideoProcessorSetStreamColorSpace1

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreamcolorspace1.md">VideoProcessorSetStreamColorSpace1</a> function.

### -field pfnVideoProcessorSetOutputShaderUsage

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputshaderusage.md">VideoProcessorSetOutputShaderUsage</a> function.

### -field pfnVideoProcessorGetBehaviorHints

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorgetbehaviorhints.md">VideoProcessorGetBehaviorHints</a> function.

### -field pfnGetCryptoSessionPrivateDataSize

The entry point for the driver's     <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md">GetCryptoSessionPrivateDataSize</a> function.

### -field pfnVideoProcessorSetOutputHDRMetaData

The entry point for the driver's VideoProcessorSetOutputHDRMetaData function.

### -field pfnVideoProcessorSetStreamHDRMetaData

The entry point for the driver's VideoProcessorSetStreamHDRMetaData function.

## -remarks

## -see-also
