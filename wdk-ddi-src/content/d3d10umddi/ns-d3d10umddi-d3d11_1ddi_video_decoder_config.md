---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODER_CONFIG
title: D3D11_1DDI_VIDEO_DECODER_CONFIG (d3d10umddi.h)
description: Describes the configuration of a Microsoft Direct3D 11 decoder device for Microsoft DirectX Video Acceleration (DXVA).
old-location: display\d3d11_1ddi_video_decoder_config.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_DECODER_CONFIG structure"]
ms.keywords: ContentKeySize, D3D11_1DDI_VIDEO_DECODER_CONFIG, D3D11_1DDI_VIDEO_DECODER_CONFIG structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODER_CONFIG, display.d3d11_1ddi_video_decoder_config, pContentKey
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_DECODER_CONFIG
f1_keywords:
 - D3D11_1DDI_VIDEO_DECODER_CONFIG
 - d3d10umddi/D3D11_1DDI_VIDEO_DECODER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_DECODER_CONFIG
---

# D3D11_1DDI_VIDEO_DECODER_CONFIG structure


## -description

Describes the configuration of a Microsoft Direct3D 11 decoder device for Microsoft DirectX Video Acceleration (DXVA).

## -struct-fields

### -field guidConfigBitstreamEncryption

Defines the encryption protocol type for bit-stream data buffers. If no encryption is applied, the value is <b>DXVA_NoEncrypt</b> (a GUID name defined in Dxva.h). If <b>ConfigBitstreamRaw</b> is 0, the value must be <b>DXVA_NoEncrypt</b>.


If set to <b>D3DWDDM2_0DDI_DECODER_ENCRYPTION_HW_CENC</b>, this indicates that the following parameters will be passed in to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a> call:

| **Value** | **Meaning** | 
|:--|:--|
| **pContentKey** | A pointer to the [D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION](./ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_begin_frame_crypto_session.md) structure, indicating which CryptoSession and the key information used to decrypt the frame. | 
| **ContentKeySize** | Set to the size of the [D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION](./ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_begin_frame_crypto_session.md) structure. |

### -field guidConfigMBcontrolEncryption

Defines the encryption protocol type for macro block control data buffers. If no encryption is applied, the value is <b>DXVA_NoEncrypt</b> (a GUID name defined in Dxva.h). If <b>ConfigBitstreamRaw</b> is 1, the value must be <b>DXVA_NoEncrypt</b>.

### -field guidConfigResidDiffEncryption

Defines the encryption protocol type for residual difference decoding data buffers (buffers containing spatial-domain data or sets of transform-domain coefficients for accelerator-based inverse discrete cosine transform [IDCT]). If no encryption is applied, the value is <b>DXVA_NoEncrypt</b> (a GUID name defined in Dxva.h). If <b>ConfigBitstreamRaw</b> is 1, the value must be <b>DXVA_NoEncrypt</b>.

### -field ConfigBitstreamRaw

Indicates whether the host-decoder sends raw bit-stream data. If the value is 1, the data for the pictures will be sent in bit-stream buffers as raw bit-stream content. If the value is 0, picture data will be sent using macroblock control command buffers. If either <b>ConfigResidDiffHost</b> or <b>ConfigResidDiffAccelerator</b> is 1, the value must be 0.

### -field ConfigMBcontrolRasterOrder

Specifies whether macroblock control commands are in raster scan order or in arbitrary order. If the value is 1, the macroblock control commands within each macroblock control command buffer are in raster-scan order. If the value is 0, the order is arbitrary. For some types of bit streams, forcing raster order either greatly increases the number of required macroblock control buffers that must be processed, or requires host reordering of the control information. Therefore, supporting arbitrary order can be more efficient.

### -field ConfigResidDiffHost

Contains the host residual difference configuration. If the value is 1, some residual difference decoding data may be sent as blocks in the spatial domain from the host. If the value is 0, spatial domain data will not be sent.

### -field ConfigSpatialResid8

Indicates the word size used to represent residual difference spatial-domain blocks for predicted (non-intra) pictures when using host-based residual difference decoding.


If <b>ConfigResidDiffHost</b> is 1 and <b>ConfigSpatialResid8</b> is 1, the host will send residual difference spatial-domain blocks for non-intra macroblocks using 8-bit signed samples and for intra macroblocks in predicted (non-intra) pictures in a format that depends on the value of <b>ConfigIntraResidUnsigned</b>:


* If <b>ConfigIntraResidUnsigned</b> is 0, spatial-domain blocks for intra macroblocks are sent as 8-bit signed integer values relative to a constant reference value of 2^(BPP–1).
* If <b>ConfigIntraResidUnsigned</b> is 1, spatial-domain blocks for intra macroblocks are sent as 8-bit unsigned integer values relative to a constant reference value of 0.


If <b>ConfigResidDiffHost</b> is 1 and <b>ConfigSpatialResid8</b> is 0, the host will send residual difference spatial-domain blocks of data for non-intra macroblocks using 16-bit signed samples and for intra macroblocks in predicted (non-intra) pictures in a format that depends on the value of <b>ConfigIntraResidUnsigned</b>:


* If <b>ConfigIntraResidUnsigned</b> is 0, spatial domain blocks for intra macroblocks are sent as 16-bit signed integer values relative to a constant reference value of 2^(BPP–1).
* If <b>ConfigIntraResidUnsigned</b> is 1, spatial domain blocks for intra macroblocks are sent as 16-bit unsigned integer values relative to a constant reference value of 0.
* If <b>ConfigResidDiffHost</b> is 0, <b>ConfigSpatialResid8</b> must be 0.
          
For intra pictures, spatial-domain blocks must be sent using 8-bit samples if bits-per-pixel (BPP) is 8, and using 16-bit samples if BPP > 8. If <b>ConfigIntraResidUnsigned</b> is 0, these samples are sent as signed integer values relative to a constant reference value of 2^(BPP–1), and if <b>ConfigIntraResidUnsigned</b> is 1, these samples are sent as unsigned integer values relative to a constant reference value of 0.

### -field ConfigResid8Subtraction

If the value is 1, 8-bit difference overflow blocks are subtracted rather than added. The value must be 0 unless <b>ConfigSpatialResid8</b> is 1.

The ability to subtract differences rather than add them enables 8-bit difference decoding to be fully compliant with the full Â±255 range of values required in video decoder specifications, because +255 cannot be represented as the addition of two signed 8-bit numbers, but any number in the range Â±255 can be represented as the difference between two signed 8-bit numbers (+255 = +127 minus –128).

### -field ConfigSpatialHost8or9Clipping

If the value is 1, spatial-domain blocks for intra macroblocks must be clipped to an 8-bit range on the host and spatial-domain blocks for non-intra macroblocks must be clipped to a 9-bit range on the host. If the value is 0, no such clipping is necessary by the host.

The value must be 0 unless <b>ConfigSpatialResid8</b> is 0 and <b>ConfigResidDiffHost</b> is 1.

### -field ConfigSpatialResidInterleaved

If the value is 1, any spatial-domain residual difference data must be sent in a chrominance-interleaved form matching the YUV format chrominance interleaving pattern. The value must be 0 unless <b>ConfigResidDiffHost</b> is 1 and the YUV format is NV12 or NV21.

### -field ConfigIntraResidUnsigned

Indicates the method of representation of spatial-domain blocks of residual difference data for intra blocks when using host-based difference decoding.

If <b>ConfigResidDiffHost</b> is 1 and <b>ConfigIntraResidUnsigned</b> is 0, spatial-domain residual difference data blocks for intra macroblocks must be sent as follows:
          

* In a non-intra picture, if ConfigSpatialResid8 is 0, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit signed integer values relative to a constant reference value of 2^(BPP–1).
* In a non-intra picture, if ConfigSpatialResid8 is 1, the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit signed integer values relative to a constant reference value of 2^(BPP–1).
* In an intra picture, if BPP is 8, the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit signed integer values relative to a constant reference value of 2^(BPP–1), regardless of the value of ConfigSpatialResid8.


If <b>ConfigResidDiffHost</b> is 1 and <b>ConfigIntraResidUnsigned</b> is 1, spatial-domain residual difference data blocks for intra macroblocks must be sent as follows:
          

* In a non-intra picture, if ConfigSpatialResid8 is 0, the spatial-domain residual difference data blocks for intra macroblocks must be sent as 16-bit unsigned integer values relative to a constant reference value of 0.
* In a non-intra picture, if ConfigSpatialResid8 is 1, the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit unsigned integer values relative to a constant reference value of 0.
* In an intra picture, if BPP is 8, the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit unsigned integer values relative to a constant reference value of 0, regardless of the value of ConfigSpatialResid8.


The value of the member must be 0 unless <b>ConfigResidDiffHost</b> is 1.

### -field ConfigResidDiffAccelerator

If the value is 1, transform-domain blocks of coefficient data may be sent from the host for accelerator-based IDCT. If the value is 0, accelerator-based IDCT will not be used. If both <b>ConfigResidDiffHost</b> and <b>ConfigResidDiffAccelerator</b> are 1, this indicates that some residual difference decoding will be done on the host and some on the accelerator, as indicated by macroblock-level control commands.

The value must be 0 if <b>ConfigBitstreamRaw</b> is 1.

### -field ConfigHostInverseScan

If the value is 1, the inverse scan for transform-domain block processing will be performed on the host, and absolute indices will be sent instead for any transform coefficients. If the value is 0, the inverse scan will be performed on the accelerator.

The value must be 0 if <b>ConfigResidDiffAccelerator</b> is 0 or if <b>Config4GroupedCoefs</b> is 1.

### -field ConfigSpecificIDCT

If the value is 1, the IDCT specified in Annex W of ITU-T Recommendation H.263 is used. If the value is 0, any compliant IDCT can be used for off-host IDCT.


The H.263 annex does not comply with the IDCT requirements of MPEG-2 corrigendum 2, so the value must not be 1 for use with MPEG-2 video.



The value must be 0 if <b>ConfigResidDiffAccelerator</b> is 0, indicating purely host-based residual difference decoding.

### -field Config4GroupedCoefs

If the value is 1, transform coefficients for off-host IDCT will be sent using the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_tcoef4group">DXVA_TCoef4Group</a> structure. If the value is 0, the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_tcoefsingle">DXVA_TCoefSingle</a> structure is used. The value must be 0 if <b>ConfigResidDiffAccelerator</b> is 0 or if <b>ConfigHostInverseScan</b> is 1.

### -field ConfigMinRenderTargetBuffCount

Specifies how many frames the decoder device processes at any one time.

### -field ConfigDecoderSpecific

Contains decoder-specific configuration information.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_begin_frame_crypto_session">D3DWDDM2_0DDI_VIDEO_DECODER_BEGIN_FRAME_CRYPTO_SESSION</a>



<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_tcoef4group">DXVA_TCoef4Group</a>



<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_tcoefsingle">DXVA_TCoefSingle</a>
