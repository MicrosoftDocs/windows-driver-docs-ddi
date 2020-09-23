---
UID: NS:d3d10umddi.D3DWDDM2_1DDI_VIDEODEVICEFUNCS
title: D3DWDDM2_1DDI_VIDEODEVICEFUNCS (d3d10umddi.h)
description: Specifies the video function table for the  Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.0 and later drivers.
ms.assetid: 25d4904c-ade7-4028-bdad-54af640b64fd
ms.date: 10/19/2018
keywords: ["D3DWDDM2_1DDI_VIDEODEVICEFUNCS structure"]
ms.keywords: D3DWDDM2_1DDI_VIDEODEVICEFUNCS, D3DWDDM2_1DDI_VIDEODEVICEFUNCS,
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
req.typenames: D3DWDDM2_1DDI_VIDEODEVICEFUNCS
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3DWDDM2_1DDI_VIDEODEVICEFUNCS
 - d3d10umddi/D3DWDDM2_1DDI_VIDEODEVICEFUNCS
topic_type:
 - apiref
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_1DDI_VIDEODEVICEFUNCS
product:
 - Windows
dev_langs:
 - c++
---

# D3DWDDM2_1DDI_VIDEODEVICEFUNCS structure


## -description

Specifies the video function table for the  Microsoft Direct3D driver device object. Used only by Windows Display Driver Model (WDDM) 2.0 and later drivers.

## -struct-fields

### -field pfnGetVideoDecoderProfileCount

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount">VideoDecoderProfileCount</a> function.

### -field pfnGetVideoDecoderProfile

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofile">VideoDecoderProfile</a> function.

### -field pfnCheckVideoDecoderFormat

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_checkvideodecoderformat">CheckVideoDecoderFormat</a> function.

### -field pfnGetVideoDecoderConfigCount

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfig">GetVideoDecoderConfig</a> function.

### -field pfnGetVideoDecoderConfig

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfig">GetVideoDecoderConfig</a> function.

### -field pfnGetVideoDecoderBufferTypeCount

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbuffertypecount">GetVideoDecoderBufferTypeCount</a> function.

### -field pfnGetVideoDecoderBufferInfo

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbufferinfo">GetVideoDecoderBufferInfo</a> function.

### -field pfnCalcPrivateVideoDecoderSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecodersize">CalcPrivateVideoDecoderSize</a> function.

### -field pfnCreateVideoDecoder

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a> function.

### -field pfnDestroyVideoDecoder

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoder">DestroyVideoDecoder</a> function.

### -field pfnVideoDecoderExtension

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderextension">VideoDecoderExtension</a> function.

### -field pfnVideoDecoderBeginFrame

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a> function.

### -field pfnVideoDecoderEndFrame

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderendframe">VideoDecoderEndFrame</a> function.

### -field pfnVideoDecoderSubmitBuffers

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers">VideoDecoderSubmitBuffers</a> function.

### -field pfnCalcPrivateVideoProcessorEnumSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorenumsize">CalcPrivateVideoProcessorEnumSize</a> function.

### -field pfnCreateVideoProcessorEnum

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.

### -field pfnDestroyVideoProcessorEnum

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorenum">DestroyVideoProcessorEnum</a> function.

### -field pfnCheckVideoProcessorFormat

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_checkvideoprocessorformat">CheckVideoProcessorFormat</a> function.

### -field pfnGetVideoProcessorCaps

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function.

### -field pfnGetVideoProcessorRateConversionCaps

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a> function.

### -field pfnGetVideoProcessorCustomRate

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate">GetVideoProcessorCustomRate</a> function.

### -field pfnGetVideoProcessorFilterRange

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorfilterrange">GetVideoProcessorFilterRange</a> function.

### -field pfnCalcPrivateVideoProcessorSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize">CalcPrivateVideoProcessorSize</a> function.

### -field pfnCreateVideoProcessor

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -field pfnDestroyVideoProcessor

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessor">DestroyVideoProcessor</a> function.

### -field pfnVideoProcessorSetOutputTargetRect

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputtargetrect">VideoProcessorSetOutputTargetRect</a> function.

### -field pfnVideoProcessorSetOutputBackgroundColor

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor">VideoProcessorSetOutputBackgroundColor</a> function.

### -field pfnVideoProcessorSetOutputColorSpace

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputcolorspace">VideoProcessorSetOutputColorSpace</a> function.

### -field pfnVideoProcessorSetOutputAlphaFillMode

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode">VideoProcessorSetOutputAlphaFillMode</a> function.

### -field pfnVideoProcessorSetOutputConstriction

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction">VideoProcessorSetOutputConstriction</a> function.

### -field pfnVideoProcessorSetOutputStereoMode

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode">VideoProcessorSetOutputStereoMode</a> function.

### -field pfnVideoProcessorSetOutputExtension

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputextension">VideoProcessorSetOutputExtension</a> function.

### -field pfnVideoProcessorGetOutputExtension

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetoutputextension">VideoProcessorGetOutputExtension</a> function.

### -field pfnVideoProcessorSetStreamFrameFormat

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamframeformat">VideoProcessorSetStreamFrameFormat</a> function.

### -field pfnVideoProcessorSetStreamColorSpace

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamcolorspace">VideoProcessorSetStreamColorSpace</a> function.

### -field pfnVideoProcessorSetStreamOutputRate

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamoutputrate">VideoProcessorSetStreamOutputRate</a> function.

### -field pfnVideoProcessorSetStreamSourceRect

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamsourcerect">VideoProcessorSetStreamSourceRect</a> function.

### -field pfnVideoProcessorSetStreamDestRect

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamdestrect">VideoProcessorSetStreamDestRect</a> function.

### -field pfnVideoProcessorSetStreamAlpha

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamalpha">VideoProcessorSetStreamAlpha</a> function.

### -field pfnVideoProcessorSetStreamPalette

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampalette">VideoProcessorSetStreamPalette</a> function.

### -field pfnVideoProcessorSetStreamPixelAspectRatio

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreampixelaspectratio">VideoProcessorSetStreamPixelAspectRatio</a> function.

### -field pfnVideoProcessorSetStreamLumaKey

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey">VideoProcessorSetStreamLumaKey</a> function.

### -field pfnVideoProcessorSetStreamStereoFormat

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a> function.

### -field pfnVideoProcessorSetStreamAutoProcessingMode

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamautoprocessingmode">VideoProcessorSetStreamAutoProcessingMode</a> function.

### -field pfnVideoProcessorSetStreamFilter

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamfilter">VideoProcessorSetStreamFilter</a> function.

### -field pfnVideoProcessorSetStreamExtension

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamextension">VideoProcessorSetStreamExtension</a> function.

### -field pfnVideoProcessorGetStreamExtension

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorgetstreamextension">VideoProcessorGetStreamExtension</a> function.

### -field pfnVideoProcessorBlt

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a> function.

### -field pfnCalcPrivateVideoDecoderOutputViewSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideodecoderoutputviewsize">CalcPrivateVideoDecoderOutputViewSize</a> function.

### -field pfnCreateVideoDecoderOutputView

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview">CreateVideoDecoderOutputView</a> function.

### -field pfnDestroyVideoDecoderOutputView

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideodecoderoutputview">DestroyVideoDecoderOutputView</a> function.

### -field pfnCalcPrivateVideoProcessorInputViewSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorinputviewsize">CalcPrivateVideoProcessorInputViewSize</a> function.

### -field pfnCreateVideoProcessorInputView

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a> function.

### -field pfnDestroyVideoProcessorInputView

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessorinputview">DestroyVideoProcessorInputView</a> function.

### -field pfnCalcPrivateVideoProcessorOutputViewSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize">CalcPrivateVideoProcessorOutputViewSize</a> function.

### -field pfnCreateVideoProcessorOutputView

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessoroutputview">CreateVideoProcessorOutputView</a> function.

### -field pfnDestroyVideoProcessorOutputView

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessoroutputview">DestroyVideoProcessorOutputView</a> function.

### -field pfnVideoProcessorInputViewReadAfterWriteHazard

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorinputviewreadafterwritehazard">VideoProcessorInputViewReadAfterWriteHazard</a> function.

### -field pfnGetContentProtectionCaps

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcontentprotectioncaps">GetContentProtectionCaps</a> function.

### -field pfnGetCryptoKeyExchangeType

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype">GetCryptoKeyExchangeType</a> function.

### -field pfnCalcPrivateCryptoSessionSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize">CalcPrivateCryptoSessionSize</a> function.

### -field pfnCreateCryptoSession

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

### -field pfnDestroyCryptoSession

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroycryptosession">DestroyCryptoSession</a> function.

### -field pfnGetCertificateSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize">GetCertificateSize</a> function.

### -field pfnGetCertificate

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificate">GetCertificate</a> function.

### -field pfnNegotiateCryptoSessionKeyExchange

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange">NegotiateCryptoSessionKeyExchange</a> function.

### -field pfnEncryptionBlt

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt">EncryptionBlt(D3D11_1)</a> function.

### -field pfnDecryptionBlt

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt">DecryptionBlt(D3D11_1)</a> function.

### -field pfnStartSessionKeyRefresh

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh">StartSessionKeyRefresh</a> function.

### -field pfnFinishSessionKeyRefresh

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a> function.

### -field pfnGetEncryptionBltKey

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey">GetEncryptionBltKey</a> function.

### -field pfnCalcPrivateAuthenticatedChannelSize

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivateauthenticatedchannelsize">CalcPrivateAuthenticatedChannelSize</a> function.

### -field pfnCreateAuthenticatedChannel

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a> function.

### -field pfnDestroyAuthenticatedChannel

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyauthenticatedchannel">DestroyAuthenticatedChannel</a> function.

### -field pfnNegotiateAuthenticatedChannelKeyExchange

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiateauthenticatedchannelkeyexchange">NegotiateAuthenticatedChannelKeyExchange</a> function.

### -field pfnQueryAuthenticatedChannel

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a> function.

### -field pfnConfigureAuthenticatedChannel

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function.

### -field pfnVideoDecoderGetHandle

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecodergethandle">VideoDecoderGetHandle</a> function.

### -field pfnCryptoSessionGetHandle

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_cryptosessiongethandle">CryptoSessionGetHandle</a> function.

### -field pfnVideoProcessorSetStreamRotation

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamrotation">VideoProcessorSetStreamRotation</a> function.

### -field pfnGetCaptureHandle

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle">GetCaptureHandle</a> function.

### -field pfnGetDataForNewHardwareKey

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_getdatafornewhardwarekey">GetDataForNewHardwareKey</a> function.

### -field pfnCheckCryptoSessionStatus

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_checkcryptosessionstatus">CheckCryptoSessionStatus</a> function.

### -field pfnVideoDecoderSubmitBuffers1

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecodersubmitbuffers1">VideoDecoderSubmitBuffers1</a> function.

### -field pfnQueryVideoCapabilities

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities">QueryVideoCapabilities</a> function.

### -field pfnCheckVideoProcessorFormatConversion

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion">CheckVideoProcessorFormatConversion</a> function.

### -field pfnVideoDecoderEnableDownsampling

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling">VideoDecoderEnableDownsampling</a> function.

### -field pfnVideoDecoderUpdateDownsampling

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderupdatedownsampling">VideoDecoderUpdateDownsampling</a> function.

### -field pfnVideoProcessorSetStreamMirror

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror">VideoProcessorSetStreamMirror</a> function.

### -field pfnVideoProcessorSetOutputColorSpace1

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputcolorspace1">VideoProcessorSetOutputColorSpace1</a> function.

### -field pfnVideoProcessorSetStreamColorSpace1

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreamcolorspace1">VideoProcessorSetStreamColorSpace1</a> function.

### -field pfnVideoProcessorSetOutputShaderUsage

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetoutputshaderusage">VideoProcessorSetOutputShaderUsage</a> function.

### -field pfnVideoProcessorGetBehaviorHints

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorgetbehaviorhints">VideoProcessorGetBehaviorHints</a> function.

### -field pfnGetCryptoSessionPrivateDataSize

The entry point for the driver's     <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize">GetCryptoSessionPrivateDataSize</a> function.

### -field pfnVideoProcessorSetOutputHDRMetaData

The entry point for the driver's [VideoProcessorSetOutputHDRMetaData](nc-d3d10umddi-pfnd3dwddm2_1ddi_videoprocessorsetoutputhdrmetadata.md) function. Added in WDDM 2.1.

### -field pfnVideoProcessorSetStreamHDRMetaData

The entry point for the driver's [VideoProcessorSetStreamHDRMetaData](nc-d3d10umddi-pfnd3dwddm2_1ddi_videoprocessorsetstreamhdrmetadata.md) function. Added in WDDM 2.1.