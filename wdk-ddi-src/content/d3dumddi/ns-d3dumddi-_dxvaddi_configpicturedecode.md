---
UID: NS:d3dumddi._DXVADDI_CONFIGPICTUREDECODE
title: DXVADDI_CONFIGPICTUREDECODE (d3dumddi.h)
description: The DXVADDI_CONFIGPICTUREDECODE structure describes the configuration for compressed picture decoding.
old-location: display\dxvaddi_configpicturedecode.htm
tech.root: display
ms.date: 07/01/2022
keywords: ["DXVADDI_CONFIGPICTUREDECODE structure"]
ms.keywords: DXVA2_Structs_23ba33fb-2b89-48c1-9455-6edc3bb8b9d3.xml, DXVADDI_CONFIGPICTUREDECODE, DXVADDI_CONFIGPICTUREDECODE structure [Display Devices], _DXVADDI_CONFIGPICTUREDECODE, d3dumddi/DXVADDI_CONFIGPICTUREDECODE, display.dxvaddi_configpicturedecode
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
targetos: Windows
req.typenames: DXVADDI_CONFIGPICTUREDECODE
f1_keywords:
 - _DXVADDI_CONFIGPICTUREDECODE
 - d3dumddi/_DXVADDI_CONFIGPICTUREDECODE
 - DXVADDI_CONFIGPICTUREDECODE
 - d3dumddi/DXVADDI_CONFIGPICTUREDECODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _DXVADDI_CONFIGPICTUREDECODE
 - DXVADDI_CONFIGPICTUREDECODE
---

# DXVADDI_CONFIGPICTUREDECODE structure

## -description

The DXVADDI_CONFIGPICTUREDECODE structure describes the configuration for compressed picture decoding.

## -struct-fields

### -field guidConfigBitstreamEncryption [in]

The encryption GUID for configuring a bitstream.

### -field guidConfigMBcontrolEncryption [in]

The encryption GUID for configuring macroblock control.

### -field guidConfigResidDiffEncryption [in]

The encryption GUID for configuring residual difference decoding.

### -field ConfigBitstreamRaw [in]

The bitstream processing indicator. A value of 1 in this member indicates that picture data is sent in bitstream buffers as raw bitstream content. A value of zero indicates that picture data is sent by using macroblock control command buffers.

Set this member to zero if the **ConfigResidDiffHost** or **ConfigResidDiffAccelerator** member is 1. A value of zero in **ConfigBitstreamRaw** is the basic level of support. The value of 1 is preferred.

### -field ConfigMBcontrolRasterOrder [in]

A UINT value that specifies whether macroblock control commands are in raster scan order or in arbitrary order. A value of 1 in this member specifies that the macroblock control commands within each macroblock control command buffer are in raster scan order. A value of zero indicates arbitrary order. A driver can restrict support to raster scan order; however, a driver should support both arbitrary and raster scan order.

### -field ConfigResidDiffHost [in]

The host residual difference configuration. A value of 1 in this member specifies that some residual difference decoding data is possibly sent as blocks in the spatial domain from the host. A value of zero specifies that spatial domain data is not sent. Set this member to zero if the **ConfigBitstreamRaw** member is 1. An accelerator should support both zero and 1.

### -field ConfigSpatialResid8 [in]

The word size that is used to represent residual difference spatial-domain blocks for predicted (nonintra) pictures when using host-based residual difference decoding (that is, when the **ConfigResidDiffHost** member is set to 1).

If **ConfigSpatialResid8** is 1 and **ConfigResidDiffHost** is 1, the host sends residual difference spatial-domain blocks for nonintra macroblocks that use 8-bit signed samples and for intra macroblocks in predicted (nonintra) pictures in a format that depends on the **ConfigIntraResidUnsigned** member as follows:

* If **ConfigIntraResidUnsigned** is zero, spatial-domain blocks for intra macroblocks are sent as 8-bit signed integer values that are relative to a constant reference value of 128.

* If **ConfigIntraResidUnsigned** is 1, spatial-domain blocks for intra macroblocks are sent as 8-bit unsigned integer values that are relative to a constant reference value of zero.

If **ConfigSpatialResid8** is zero and **ConfigResidDiffHost** is 1, the host sends residual difference spatial-domain blocks of data for nonintra macroblocks that use 16-bit signed samples and for intra macroblocks in predicted (nonintra) pictures in a format that depends on **ConfigIntraResidUnsigned** as follows:

* If **ConfigIntraResidUnsigned** is zero, spatial domain blocks for intra macroblocks are sent as 16-bit signed integer values that are relative to a constant reference value of 2^(BPP-1), where *BPP* is the number of bits per sample for the uncompressed video (generally a value of 8).

* If **ConfigIntraResidUnsigned** is 1, spatial domain blocks for intra macroblocks are sent as 16-bit unsigned integer values that are relative to a constant reference value of zero.

**ConfigSpatialResid8** must be zero if **ConfigResidDiffHost** is zero. If **ConfigResidDiffHost** is 1, **ConfigSpatialResid8** can be any value.

> [!NOTE]
> For intra pictures with *BPP* equal to 8, spatial-domain blocks must be sent by using 8-bit samples. For intra pictures with *BPP* greater than 8, spatial-domain blocks must be sent by using 16-bit samples.
> If **ConfigIntraResidUnsigned** is zero, these samples are sent as signed integer values that are relative to a constant reference value of 2^(BPP-1). If **ConfigIntraResidUnsigned** is 1, these samples are sent as unsigned integer values that are relative to a constant reference value of zero.

### -field ConfigResid8Subtraction [in]

A UINT value that specifies whether 8-bit difference overflow blocks are subtracted or added. If this member is set to 1, 8-bit difference overflow blocks are subtracted rather than added. This member must be zero unless **ConfigSpatialResid8** is 1. If **ConfigSpatialResid8** is 1, the preferred value for **ConfigResid8Subtraction** is 1. The ability to subtract differences rather than to add them enables 8-bit difference decoding to be fully compliant with the range from -255 through +255 of values that are required in video decoder specifications. This ability enables full compliance because +255 cannot be represented as the addition of two signed 8-bit numbers but any number in the range from -255 through +255 can be represented as the difference between two signed 8-bit numbers (+255 is equal to +127 minus -128).

### -field ConfigSpatialHost8or9Clipping [in]

A UINT value that specifies whether clipping is performed by the host. If this member set to 1, spatial-domain blocks for intra macroblocks are clipped to an 8-bit range on the host and spatial-domain blocks for nonintra macroblocks are clipped to a 9-bit range on the host. A value of zero indicates that no such clipping is performed by the host. This member must be zero unless **ConfigSpatialResid8** is set to zero and **ConfigResidDiffHost** is set to 1. The preferred value for **ConfigSpatialHost8or9Clipping** is zero.

### -field ConfigSpatialResidInterleaved [in]

A UINT value that specifies whether spatial-domain residual difference data is sent in a chrominance-interleaved form. If this member is set to 1, any spatial-domain residual difference data is sent in a chrominance-interleaved form that matches the YUV format chrominance interleaving pattern. This member must be zero unless **ConfigResidDiffHost** is 1 and the YUV format is NV12 or NV21. The preferred value for **ConfigSpatialResidInterleaved** is zero.

### -field ConfigIntraResidUnsigned [in]

The method of representation of spatial-domain blocks of residual difference data for intra blocks when using host-based difference decoding (that is, when the **ConfigResidDiffHost** member is equal to 1).

If **ConfigIntraResidUnsigned** is set to zero and **ConfigResidDiffHost** is set to 1, spatial-domain residual difference data blocks for intra macroblocks are sent as follows:

* In a nonintra picture if the **ConfigSpatialResid8** member is zero, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit signed integer values that are relative to a constant reference value of 2^(BPP-1), where *BPP* is the number of bits per sample for the uncompressed video (generally a value of 8).

* In a nonintra picture if **ConfigSpatialResid8** is 1 and in an intra picture if *BPP* is equal to 8 (regardless of the value of **ConfigSpatialResid8**), the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit signed integer values that are relative to a constant reference value of 128.

If **ConfigIntraResidUnsigned** is set to 1 and **ConfigResidDiffHost** is set to 1, spatial-domain residual difference data blocks for intra macroblocks are sent as follows:

* In a nonintra picture if **ConfigSpatialResid8** is zero, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit unsigned integer values that are relative to a constant reference value of zero.

* In a nonintra picture if **ConfigSpatialResid8** is 1 and in an intra picture if *BPP* is equal to 8 (regardless of the value of **ConfigSpatialResid8**), the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit unsigned integer values that are relative to a constant reference value of zero.

**ConfigIntraResidUnsigned** must be zero unless **ConfigResidDiffHost** is 1. The preferred value for **ConfigIntraResidUnsigned** is zero.

### -field ConfigResidDiffAccelerator [in]

The accelerator residual difference configuration. A value of 1 in this member indicates that transform-domain blocks of coefficient data can be sent from the host for accelerator-based IDCT. A value of zero indicates that accelerator-based IDCT is not used.

If both the **ConfigResidDiffHost** member and **ConfigResidDiffAccelerator** are 1, some residual difference decoding is performed on the host and some on the accelerator, as indicated by macroblock-level control commands. **ConfigResidDiffAccelerator** must be zero if the **bConfigBitstreamRaw** member is 1.

The preferred value for **ConfigResidDiffAccelerator** is 1.

If **ConfigResidDiffAccelerator** and **ConfigResidDiffHost** are set to 1, residual difference decoding can be shared between the host and accelerator on a macroblock basis. This sharing is an even higher level of accelerator capability than when **ConfigResidDiffAccelerator** is set to 1 and **ConfigResidDiffHost** is set to zero.

### -field ConfigHostInverseScan [in]

A UINT value that specifies whether the inverse scan for transform-domain block processing is performed on the host or the accelerator. A value of 1 in this member indicates that the inverse scan for transform-domain block processing is performed on the host, and absolute indexes are sent instead for any transform coefficients. A value of zero indicates that inverse scan is performed on the accelerator. **ConfigHostInverseScan** must be zero if **ConfigResidDiffAccelerator** is zero or if the **Config4GroupedCoefs** member is 1.

The preferred value for **ConfigHostInverseScan** is 1 if **ConfigResidDiffAccelerator** is 1.

### -field ConfigSpecificIDCT [in]

A UINT value that specifies the use of a specific IDCT method for [off-host IDCT](/windows-hardware/drivers/display/off-host-idct). A value of 1 in this member indicates the use of the IDCT that is specified in Annex W of ITU-T Recommendation H.263, which you can learn about from the [International Telecommunication Union](https://www.itu.int/rec/R-REC-BT.601/) website. A value of zero indicates that any compliant IDCT can be used for off-host IDCT. (Values other than zero and 1 are reserved.)

**ConfigSpecificIDCT** must be zero if **ConfigResidDiffAccelerator** is zero, which indicates host-based residual difference decoding.

> [!NOTE]
> **ConfigSpecificIDCT** must not be set to 1 for use with MPEG-2 video.

### -field Config4GroupedCoefs [in]

A UINT value that specifies how transform coefficients for off-host IDCT are sent. A value of 1 in this member indicates that transform coefficients for off-host IDCT are sent by using the [**DXVA_TCoef4Group**](../dxva/ns-dxva-_dxva_tcoef4group.md) structure rather than the [**DXVA_TCoefSingle**](../dxva/ns-dxva-_dxva_tcoefsingle.md) structure. **Config4GroupedCoefs** is zero if **ConfigResidDiffAccelerator** is zero or if **ConfigHostInverseScan** is 1.

The preferred value for **Config4GroupedCoefs** is zero if **ConfigResidDiffAccelerator** is 1.

### -field ConfigMinRenderTargetBuffCount [in]

A USHORT value that specifies the minimum number of render target buffers.

### -field ConfigDecoderSpecific [in]

A USHORT value that specifies decoder-specific features to configure. For information about a decoder's features, see the specification for that decoder. For a list of decoders, see [Providing Capabilities for Video Decoding](/windows-hardware/drivers/display/providing-capabilities-for-video-decoding).

## -see-also

[**D3DDDIARG_GETCAPS**](ns-d3dumddi-_d3dddiarg_getcaps.md)

[**D3DDDICAPS_TYPE**](ne-d3dumddi-_d3dddicaps_type.md)

[**GetCaps**](nc-d3dumddi-pfnd3dddi_getcaps.md)
