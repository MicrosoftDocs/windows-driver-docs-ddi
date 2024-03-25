---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEODEVICEFUNCS
title: D3DWDDM2_4DDI_VIDEODEVICEFUNCS (d3d10umddi.h)
description: The D3DWDDM2_4DDI_VIDEODEVICEFUNCS structure specifies the video function table for the Microsoft Direct3D driver device object.
ms.date: 01/17/2023
keywords: ["D3DWDDM2_4DDI_VIDEODEVICEFUNCS structure"]
ms.keywords: D3DWDDM2_4DDI_VIDEODEVICEFUNCS, D3DWDDM2_4DDI_VIDEODEVICEFUNCS,
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
req.typenames: D3DWDDM2_4DDI_VIDEODEVICEFUNCS
targetos: Windows
tech.root: display
f1_keywords:
 - D3DWDDM2_4DDI_VIDEODEVICEFUNCS
 - d3d10umddi/D3DWDDM2_4DDI_VIDEODEVICEFUNCS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_4DDI_VIDEODEVICEFUNCS
---

# D3DWDDM2_4DDI_VIDEODEVICEFUNCS structure

## -description

The **D3DWDDM2_4DDI_VIDEODEVICEFUNCS** structure specifies the video function table for the Direct3D driver device object. This structure is used only by WDDM 2.4 and later drivers.

The driver must support the WDDM 2.4 version of the user-mode DDI. When the DDI is supported, the runtime will call [**PFND3D10DDI_RETRIEVESUBOBJECT**](nc-d3d10umddi-pfnd3d10ddi_retrievesubobject.md) to retrieve the **D3DWDDM2_4DDI_VIDEODEVICEFUNCS** video device functions.

## -struct-fields

### -field pfnGetVideoDecoderProfileCount

The entry point for the driver's [**GetVideoDecoderProfileCount**](nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount.md) function.

### -field pfnGetVideoDecoderProfile

The entry point for the driver's [**GetVideoDecoderProfile**](nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofile.md) function.

### -field pfnCheckVideoDecoderFormat

The entry point for the driver's [**CheckVideoDecoderFormat**](nc-d3d10umddi-pfnd3d11_1ddi_checkvideodecoderformat.md) function.

### -field pfnGetVideoDecoderConfigCount

The entry point for the driver's [**GetVideoDecoderConfigCount**](nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount.md) function.

### -field pfnGetVideoDecoderConfig

The entry point for the driver's [**GetVideoDecoderConfig**](nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfig.md) function.

### -field pfnGetVideoDecoderBufferTypeCount

The entry point for the driver's [**GetVideoDecoderBufferTypeCount**](nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbuffertypecount.md) function.

### -field pfnGetVideoDecoderBufferInfo

The entry point for the driver's [**GetVideoDecoderBufferInfo**](nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbufferinfo.md) function.

### -field pfnCalcPrivateVideoDecoderSize

The entry point for the driver's [**CalcPrivateVideoDecoderSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize.md) function.

### -field pfnCreateVideoDecoder

The entry point for the driver's [**CreateVideoDecoder**](nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md) function.

### -field pfnDestroyVideoDecoder

The entry point for the driver's [**DestroyVideoDecoder**](nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoder.md) function.

### -field pfnVideoDecoderExtension

The entry point for the driver's [**VideoDecoderExtension**](nc-d3d10umddi-pfnd3d11_1ddi_videodecoderextension.md) function.

### -field pfnVideoDecoderBeginFrame

The entry point for the driver's [**VideoDecoderBeginFrame**](nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md) function.

### -field pfnVideoDecoderEndFrame

The entry point for the driver's [**VideoDecoderEndFrame**](nc-d3d10umddi-pfnd3d11_1ddi_videodecoderendframe.md) function.

### -field pfnVideoDecoderSubmitBuffers

The entry point for the driver's [**VideoDecoderSubmitBuffers**](nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers.md) function.

### -field pfnCalcPrivateVideoProcessorEnumSize

The entry point for the driver's [**CalcPrivateVideoProcessorEnumSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorenumsize.md) function.

### -field pfnCreateVideoProcessorEnum

The entry point for the driver's [**CreateVideoProcessorEnum**](nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md) function.

### -field pfnDestroyVideoProcessorEnum

The entry point for the driver's [**DestroyVideoProcessorEnum**](nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorenum.md) function.

### -field pfnCheckVideoProcessorFormat

The entry point for the driver's [**CheckVideoProcessorFormat**](nc-d3d10umddi-pfnd3d11_1ddi_checkvideoprocessorformat.md) function.

### -field pfnGetVideoProcessorCaps

The entry point for the driver's [**GetVideoProcessorCaps**](nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md) function.

### -field pfnGetVideoProcessorRateConversionCaps

The entry point for the driver's [**GetVideoProcessorRateConversionCaps**](nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md) function.

### -field pfnGetVideoProcessorCustomRate

The entry point for the driver's [**GetVideoProcessorCustomRate**](nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md) function.

### -field pfnGetVideoProcessorFilterRange

The entry point for the driver's [**GetVideoProcessorFilterRange**](nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorfilterrange.md) function.

### -field pfnCalcPrivateVideoProcessorSize

The entry point for the driver's [**CalcPrivateVideoProcessorSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize.md) function.

### -field pfnCreateVideoProcessor

The entry point for the driver's [**CreateVideoProcessor**](nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md) function.

### -field pfnDestroyVideoProcessor

The entry point for the driver's [**DestroyVideoProcessor**](nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessor.md) function.

### -field pfnVideoProcessorSetOutputTargetRect

The entry point for the driver's [**VideoProcessorSetOutputTargetRect**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputtargetrect.md) function.

### -field pfnVideoProcessorSetOutputBackgroundColor

The entry point for the driver's [**VideoProcessorSetOutputBackgroundColor**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor.md) function.

### -field pfnVideoProcessorSetOutputColorSpace

The entry point for the driver's [**VideoProcessorSetOutputColorSpace**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputcolorspace.md) function.

### -field pfnVideoProcessorSetOutputAlphaFillMode

The entry point for the driver's [**VideoProcessorSetOutputAlphaFillMode**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md) function.

### -field pfnVideoProcessorSetOutputConstriction

The entry point for the driver's [**VideoProcessorSetOutputConstriction**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md) function.

### -field pfnVideoProcessorSetOutputStereoMode

The entry point for the driver's [**VideoProcessorSetOutputStereoMode**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode.md) function.

### -field pfnVideoProcessorSetOutputExtension

The entry point for the driver's [**VideoProcessorSetOutputExtension**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputextension.md) function.

### -field pfnVideoProcessorGetOutputExtension

The entry point for the driver's [**VideoProcessorGetOutputExtension**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetoutputextension.md) function.

### -field pfnVideoProcessorSetStreamFrameFormat

The entry point for the driver's [**VideoProcessorSetStreamFrameFormat**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamframeformat.md) function.

### -field pfnVideoProcessorSetStreamColorSpace

The entry point for the driver's [**VideoProcessorSetStreamColorSpace**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamcolorspace.md) function.

### -field pfnVideoProcessorSetStreamOutputRate

The entry point for the driver's [**VideoProcessorSetStreamOutputRate**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamoutputrate.md) function.

### -field pfnVideoProcessorSetStreamSourceRect

The entry point for the driver's [**VideoProcessorSetStreamSourceRect**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamsourcerect.md) function.

### -field pfnVideoProcessorSetStreamDestRect

The entry point for the driver's [**VideoProcessorSetStreamDestRect**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamdestrect.md) function.

### -field pfnVideoProcessorSetStreamAlpha

The entry point for the driver's [**VideoProcessorSetStreamAlpha**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamalpha.md) function.

### -field pfnVideoProcessorSetStreamPalette

The entry point for the driver's [**VideoProcessorSetStreamPalette**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampalette.md) function.

### -field pfnVideoProcessorSetStreamPixelAspectRatio

The entry point for the driver's [**VideoProcessorSetStreamPixelAspectRatio**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampixelaspectratio.md) function.

### -field pfnVideoProcessorSetStreamLumaKey

The entry point for the driver's [**VideoProcessorSetStreamLumaKey**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md) function.

### -field pfnVideoProcessorSetStreamStereoFormat

The entry point for the driver's [**VideoProcessorSetStreamStereoFormat**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md) function.

### -field pfnVideoProcessorSetStreamAutoProcessingMode

The entry point for the driver's [**VideoProcessorSetStreamAutoProcessingMode**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamautoprocessingmode.md) function.

### -field pfnVideoProcessorSetStreamFilter

The entry point for the driver's [**VideoProcessorSetStreamFilter**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamfilter.md) function.

### -field pfnVideoProcessorSetStreamExtension

The entry point for the driver's [**VideoProcessorSetStreamExtension**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamextension.md) function.

### -field pfnVideoProcessorGetStreamExtension

The entry point for the driver's [**VideoProcessorGetStreamExtension**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetstreamextension.md) function.

### -field pfnVideoProcessorBlt

The entry point for the driver's [**VideoProcessorBlt**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md) function.

### -field pfnCalcPrivateVideoDecoderOutputViewSize

The entry point for the driver's [**CalcPrivateVideoDecoderOutputViewSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecoderoutputviewsize.md) function.

### -field pfnCreateVideoDecoderOutputView

The entry point for the driver's [**CreateVideoDecoderOutputView**](nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md) function.

### -field pfnDestroyVideoDecoderOutputView

The entry point for the driver's [**DestroyVideoDecoderOutputView**](nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoderoutputview.md) function.

### -field pfnCalcPrivateVideoProcessorInputViewSize

The entry point for the driver's [**CalcPrivateVideoProcessorInputViewSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorinputviewsize.md) function.

### -field pfnCreateVideoProcessorInputView

The entry point for the driver's [**CreateVideoProcessorInputView**](nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md) function.

### -field pfnDestroyVideoProcessorInputView

The entry point for the driver's [**DestroyVideoProcessorInputView**](nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorinputview.md) function.

### -field pfnCalcPrivateVideoProcessorOutputViewSize

The entry point for the driver's [**CalcPrivateVideoProcessorOutputViewSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md) function.

### -field pfnCreateVideoProcessorOutputView

The entry point for the driver's [**CreateVideoProcessorOutputView**](nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessoroutputview.md) function.

### -field pfnDestroyVideoProcessorOutputView

The entry point for the driver's [**DestroyVideoProcessorOutputView**](nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessoroutputview.md) function.

### -field pfnVideoProcessorInputViewReadAfterWriteHazard

The entry point for the driver's [**VideoProcessorInputViewReadAfterWriteHazard**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorinputviewreadafterwritehazard.md) function.

### -field pfnGetContentProtectionCaps

The entry point for the driver's [**GetContentProtectionCaps**](nc-d3d10umddi-pfnd3d11_1ddi_getcontentprotectioncaps.md) function.

### -field pfnGetCryptoKeyExchangeType

The entry point for the driver's [**GetCryptoKeyExchangeType**](nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype.md) function.

### -field pfnCalcPrivateCryptoSessionSize

The entry point for the driver's [**CalcPrivateCryptoSessionSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize.md) function.

### -field pfnCreateCryptoSession

The entry point for the driver's [**CreateCryptoSession**](nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md) function.

### -field pfnDestroyCryptoSession

The entry point for the driver's [**DestroyCryptoSession**](nc-d3d10umddi-pfnd3d11_1ddi_destroycryptosession.md) function.

### -field pfnGetCertificateSize

The entry point for the driver's [**GetCertificateSize**](nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md) function.

### -field pfnGetCertificate

The entry point for the driver's [**GetCertificate**](nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md) function.

### -field pfnNegotiateCryptoSessionKeyExchange

The entry point for the driver's [**NegotiateCryptoSessionKeyExchange**](nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md) function.

### -field pfnEncryptionBlt

The entry point for the driver's [**EncryptionBlt(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md) function.

### -field pfnDecryptionBlt

The entry point for the driver's [**DecryptionBlt(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt.md) function.

### -field pfnStartSessionKeyRefresh

The entry point for the driver's [**StartSessionKeyRefresh**](nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh.md) function.

### -field pfnFinishSessionKeyRefresh

The entry point for the driver's [**FinishSessionKeyRefresh**](nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md) function.

### -field pfnGetEncryptionBltKey

The entry point for the driver's [**GetEncryptionBltKey**](nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey.md) function.

### -field pfnCalcPrivateAuthenticatedChannelSize

The entry point for the driver's [**CalcPrivateAuthenticatedChannelSize**](nc-d3d10umddi-pfnd3d11_1ddi_calcprivateauthenticatedchannelsize.md) function.

### -field pfnCreateAuthenticatedChannel

The entry point for the driver's [**CreateAuthenticatedChannel(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md) function.

### -field pfnDestroyAuthenticatedChannel

The entry point for the driver's [**DestroyAuthenticatedChannel**](nc-d3d10umddi-pfnd3d11_1ddi_destroyauthenticatedchannel.md) function.

### -field pfnNegotiateAuthenticatedChannelKeyExchange

The entry point for the driver's [**NegotiateAuthenticatedChannelKeyExchange**](nc-d3d10umddi-pfnd3d11_1ddi_negotiateauthenticatedchannelkeyexchange.md) function.

### -field pfnQueryAuthenticatedChannel

The entry point for the driver's [**QueryAuthenticatedChannel(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md) function.

### -field pfnConfigureAuthenticatedChannel

The entry point for the driver's [**ConfigureAuthenticatedChannel(D3D11_1)**](nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md) function.

### -field pfnVideoDecoderGetHandle

The entry point for the driver's [**VideoDecoderGetHandle**](nc-d3d10umddi-pfnd3d11_1ddi_videodecodergethandle.md) function.

### -field pfnCryptoSessionGetHandle

The entry point for the driver's [**CryptoSessionGetHandle**](nc-d3d10umddi-pfnd3d11_1ddi_cryptosessiongethandle.md) function.

### -field pfnVideoProcessorSetStreamRotation

The entry point for the driver's [**VideoProcessorSetStreamRotation**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamrotation.md) function.

### -field pfnGetCaptureHandle

The entry point for the driver's [**GetCaptureHandle**](nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md) function.

### -field pfnGetDataForNewHardwareKey

The entry point for the driver's [**GetDataForNewHardwareKey**](nc-d3d10umddi-pfnd3dwddm2_0ddi_getdatafornewhardwarekey.md) function.

### -field pfnCheckCryptoSessionStatus

The entry point for the driver's [**CheckCryptoSessionStatus**](nc-d3d10umddi-pfnd3dwddm2_0ddi_checkcryptosessionstatus.md) function.

### -field pfnVideoDecoderSubmitBuffers2

The entry point for the driver's [**VideoDecoderSubmitBuffers2**](nc-d3d10umddi-pfnd3dwddm2_4ddi_videodecodersubmitbuffers.md) function.

### -field pfnQueryVideoCapabilities

The entry point for the driver's [**QueryVideoCapabilities**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md) function.

### -field pfnCheckVideoProcessorFormatConversion

The entry point for the driver's [**CheckVideoProcessorFormatConversion**](nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion.md) function.

### -field pfnVideoDecoderEnableDownsampling

The entry point for the driver's [**VideoDecoderEnableDownsampling**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling.md) function.

### -field pfnVideoDecoderUpdateDownsampling

The entry point for the driver's [**VideoDecoderUpdateDownsampling**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderupdatedownsampling.md) function.

### -field pfnVideoProcessorSetStreamMirror

The entry point for the driver's [**VideoProcessorSetStreamMirror**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md) function.

### -field pfnVideoProcessorSetOutputColorSpace1

The entry point for the driver's [**VideoProcessorSetOutputColorSpace1**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputcolorspace1.md) function.

### -field pfnVideoProcessorSetStreamColorSpace1

The entry point for the driver's [**VideoProcessorSetStreamColorSpace1**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreamcolorspace1.md) function.

### -field pfnVideoProcessorSetOutputShaderUsage

The entry point for the driver's [**VideoProcessorSetOutputShaderUsage**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputshaderusage.md) function.

### -field pfnVideoProcessorGetBehaviorHints

The entry point for the driver's [**VideoProcessorGetBehaviorHints**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorgetbehaviorhints.md) function.

### -field pfnGetCryptoSessionPrivateDataSize

The entry point for the driver's [**GetCryptoSessionPrivateDataSize**](nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md) function.

### -field pfnVideoProcessorSetOutputHDRMetaData

The entry point for the driver's [**VideoProcessorSetOutputHDRMetaData**](nc-d3d10umddi-pfnd3dwddm2_1ddi_videoprocessorsetoutputhdrmetadata.md) function.

### -field pfnVideoProcessorSetStreamHDRMetaData

The entry point for the driver's [**VideoProcessorSetStreamHDRMetaData**](nc-d3d10umddi-pfnd3dwddm2_1ddi_videoprocessorsetstreamhdrmetadata.md) function.

### -field pfnNegotiateCryptoSessionKeyExchangeMT

The entry point for the driver's [**NegotiateCryptoSessionKeyExchangeMT**](nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md) function.
