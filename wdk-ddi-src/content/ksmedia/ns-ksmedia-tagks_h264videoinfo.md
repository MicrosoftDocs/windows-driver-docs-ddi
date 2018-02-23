---
UID: NS:ksmedia.tagKS_H264VIDEOINFO
title: tagKS_H264VIDEOINFO
author: windows-driver-content
description: The KS_H264VIDEOINFO describes the device capabilities that apply to the current media type.
old-location: stream\ks_h264videoinfo.htm
old-project: stream
ms.assetid: 1EBA2124-F5D3-4683-B967-8179CCCD3102
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: tagKS_H264VIDEOINFO, KS_H264VIDEOINFO, stream.ks_h264videoinfo, ksmedia/PKS_H264VIDEOINFO, *PKS_H264VIDEOINFO, PKS_H264VIDEOINFO structure pointer [Streaming Media Devices], ksmedia/KS_H264VIDEOINFO, KS_H264VIDEOINFO structure [Streaming Media Devices], PKS_H264VIDEOINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	Ksmedia.h
apiname:
-	KS_H264VIDEOINFO
product: Windows
targetos: Windows
req.typenames: "*PKS_H264VIDEOINFO, KS_H264VIDEOINFO"
---

# tagKS_H264VIDEOINFO structure


## -description


The KS_H264VIDEOINFO describes the device capabilities that apply to the current media type.


## -syntax


````
typedef struct _KS_H264VIDEOINFO {
  WORD  wWidth;
  WORD  wHeight;
  WORD  wSARwidth;
  WORD  wSARheight;
  WORD  wProfile;
  BYTE  bLevelIDC;
  WORD  wConstrainedToolset;
  DWORD bmSupportedUsages;
  WORD  bmCapabilities;
  DWORD bmSVCCapabilities;
  DWORD bmMVCCapabilities;
  DWORD dwFrameInterval;
  BYTE  bMaxCodecConfigDelay;
  BYTE  bmSupportedSliceModes;
  BYTE  bmSupportedSyncFrameTypes;
  BYTE  bDynamicResolutionScaling;
  BYTE  bSimulcastSupport;
  BYTE  bmSupportedRateControlModes;
  DWORD dwMaxMBperSecOneResolutionNoScalability;
  DWORD dwMaxMBperSecTwoResolutionsNoScalability;
  DWORD dwMaxMBperSecThreeResolutionsNoScalability;
  DWORD dwMaxMBperSecFourResolutionsNoScalability;
  DWORD dwMaxMBperSecOneResolutionTemporalScalability;
  DWORD dwMaxMBperSecTwoResolutionsTemporalScalablility;
  DWORD dwMaxMBperSecThreeResolutionsTemporalScalability;
  DWORD dwMaxMBperSecFourResolutionsTemporalScalability;
  DWORD dwMaxMBperSecOneResolutionTemporalQualityScalability;
  DWORD dwMaxMBperSecTwoResolutionsTemporalQualityScalability;
  DWORD dwMaxMBperSecThreeResolutionsTemporalQualityScalablity;
  DWORD dwMaxMBperSecFourResolutionsTemporalQualityScalability;
  DWORD dwMaxMBperSecOneResolutionFullScalability;
  DWORD dwMaxMBperSecTwoResolutionsFullScalability;
  DWORD dwMaxMBperSecThreeResolutionsFullScalability;
  DWORD dwMaxMBperSecFourResolutionsFullScalability;
} KS_H264VIDEOINFO, *PKS_H264VIDEOINFO;
````


## -struct-fields




### -field wWidth

Specifies the width in pixels of pictures output from the decoding process. 

<div class="alert"><b>Note</b>  The value for this member must be a multiple of 2, but it does not have to be an integer multiple of 16. It can be specified using a frame cropping rectangle in the active Sequence Parameter Set (SPS).</div>
<div> </div>

### -field wHeight

Specifies the height in pixels of pictures output from the decoding process.

<div class="alert"><b>Note</b>   The value for this member must be a multiple of 2. When field coding or frame/field adaptive coding is used, it must be a multiple of 4. It does not have to be an integer multiple of 16. It can be specified using a frame cropping rectangle in the active SPS.</div>
<div> </div>

### -field wSARwidth

Specifies the sample aspect ratio width as defined in the H.264 Annex E. 

<div class="alert"><b>Note</b>  It must  be relatively prime with respect to <b>wSARheight</b>.</div>
<div> </div>

### -field wSARheight

Specifies the sample aspect ratio height as defined in the H.264 Annex E. 

<div class="alert"><b>Note</b>  It must be relatively prime with respect to <b>bSARwidth</b>.</div>
<div> </div>

### -field wProfile

Specifies the first two bytes of the sequence parameter set as described by profile_idc and constraint flags in the H.264 specification. 

<div class="alert"><b>Note</b>  This member indicates the profile and applicable constraints to be used. </div>
<div> </div>
The following are examples of allowed values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x4240</td>
<td>Constrained Baseline Profile.</td>
</tr>
<tr>
<td>0x4200</td>
<td>Baseline Profile.</td>
</tr>
<tr>
<td>0x4D00</td>
<td>Main Profile.</td>
</tr>
<tr>
<td>0x6400</td>
<td>High Profile.</td>
</tr>
<tr>
<td>0x5300</td>
<td>Scalable Baseline Profile.</td>
</tr>
<tr>
<td>0x5600</td>
<td>Scalable High Profile.</td>
</tr>
<tr>
<td>0x7600</td>
<td>Multiview High Profile.</td>
</tr>
<tr>
<td>0x8000</td>
<td>Stereo High Profile.</td>
</tr>
</table>
 


### -field bLevelIDC

Specifies the level as described by the level_idc flag.

<div class="alert"><b>Note</b>  This member indicates the minimum level that supports the resolution and the maximum bit rate for this frame descriptor.</div>
<div> </div>
The following are examples of allowed values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x1F</td>
<td>Level 3.1.</td>
</tr>
<tr>
<td>0x28</td>
<td>Level 4.0.</td>
</tr>
</table>
 


### -field wConstrainedToolset

Constrains the features allowed by <b>wProfile</b>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>No constraints. All tools defined by the selected <b>wProfile</b> and the bmSetting set are allowed.</td>
</tr>
<tr>
<td>1</td>
<td>Unified Communication (UC) Constrained High Toolset. </td>
</tr>
<tr>
<td>2</td>
<td>UC Scalable Constrained High1.</td>
</tr>
<tr>
<td>3</td>
<td>UC Scalable Constrained Baseline1.</td>
</tr>
<tr>
<td>4 to 65535</td>
<td>Reserved.</td>
</tr>
</table>
 


### -field bmSupportedUsages

Defines the bitmap that specifies the supported usages.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D0</td>
<td>Real-time/UCConfig (Unified Communication Configuration) mode 0.</td>
</tr>
<tr>
<td>D1</td>
<td>Real-time/UCConfig mode 1.</td>
</tr>
<tr>
<td>D2</td>
<td>Real-time/UCConfig mode 2Q.</td>
</tr>
<tr>
<td>D3</td>
<td>Real-time/UCConfig mode 2S.</td>
</tr>
<tr>
<td>D4</td>
<td>Real-time/UCConfig mode 3.</td>
</tr>
<tr>
<td>D7-D5</td>
<td>Reserved; set to 0.</td>
</tr>
<tr>
<td>D15-D8</td>
<td>Broadcast modes.</td>
</tr>
<tr>
<td>D16</td>
<td>File storage mode with I and P slices (for example, IPPP).</td>
</tr>
<tr>
<td>D17</td>
<td>File storage mode with I, P and B slices (for example, IB...IP).</td>
</tr>
<tr>
<td>D18</td>
<td>File storage all-I-frame mode.</td>
</tr>
<tr>
<td>D23-D19</td>
<td>Reserved; set to 0.</td>
</tr>
<tr>
<td>D24</td>
<td>MVC Stereo High Mode.</td>
</tr>
<tr>
<td>D25</td>
<td>MVC Multiview Mode.</td>
</tr>
<tr>
<td>D31-D26</td>
<td>Reserved; set to 0.</td>
</tr>
</table>
 


### -field bmCapabilities

Defines the bitmap that specifies the capabilities for this frame descriptor.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D0</td>
<td>Context based Adaptive Variable Length Coding (CAVLC ) only.</td>
</tr>
<tr>
<td>D1</td>
<td>Context based Adaptive Binary Arithmetic Coding (CABAC) only.</td>
</tr>
<tr>
<td>D2</td>
<td>Constant frame rate.</td>
</tr>
<tr>
<td>D3</td>
<td>Separate QP for luma/chroma.</td>
</tr>
<tr>
<td>D4</td>
<td>Separate QP for Cb/Cr.</td>
</tr>
<tr>
<td>D5</td>
<td>No picture reordering.</td>
</tr>
<tr>
<td>D15-D6</td>
<td>Reserved; set to 0.</td>
</tr>
</table>
 


### -field bmSVCCapabilities

Defines the bitmap that specifies the Scalable Video Coding (SVC) capabilities.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D2-D0</td>
<td>Maximum number of temporal layers minus 1.</td>
</tr>
<tr>
<td>D3</td>
<td>Rewrite support. </td>
</tr>
<tr>
<td>D6-D4</td>
<td>Maximum number of Coarse Grained Scalability (CGS) layers minus 1. </td>
</tr>
<tr>
<td>D9-D7</td>
<td>Maximum number of Medium Grained Scalability (MGS) sublayers.</td>
</tr>
<tr>
<td>D10</td>
<td>Additional SNR scalability support in spatial enhancement layers. </td>
</tr>
<tr>
<td>D13-D11</td>
<td>Maximum number of spatial layers minus 1.</td>
</tr>
<tr>
<td>D31-D14</td>
<td>Reserved.</td>
</tr>
</table>
 


### -field bmMVCCapabilities

Defines the bitmap that specifies the Multicast Video Coding (MVC) capabilities. 

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D2-D0</td>
<td>Maximum number of temporal layers minus 1.</td>
</tr>
<tr>
<td>D11-D3</td>
<td>Maximum number of view components minus 1.</td>
</tr>
<tr>
<td>D31-D11</td>
<td>Reserved.</td>
</tr>
</table>
 


### -field dwFrameInterval

Specifies the supported frame interval.

<div class="alert"><b>Note</b>  This is the shortest frame interval supported, at the highest frame rate, in 100-nanoseconds units. </div>
<div> </div>

### -field bMaxCodecConfigDelay

Specifies the maximum number of frames the encoder takes to respond to a command.


### -field bmSupportedSliceModes

Defines the bitmap that specifies the slice modes.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D0</td>
<td>Slice mode 0.</td>
</tr>
<tr>
<td>D1</td>
<td>Slice mode 1.</td>
</tr>
<tr>
<td>D7-D2</td>
<td>Reserved.</td>
</tr>
</table>
 


### -field bmSupportedSyncFrameTypes


### -field bResolutionScaling

 


### -field bSimulcastSupport

Specifies the number of H.264 video streaming endpoints and the number of streams this endpoint supports.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>One endpoint and one stream.</td>
</tr>
<tr>
<td>1</td>
<td>One endpoint and multiple streams.</td>
</tr>
</table>
 


### -field bmSupportedRateControlModes

Defines the bitmap that specifies the rate control modes. 

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D0</td>
<td>Variable Bit Rate (VBR) without underflow (H.264 low_delay_hrd_flag = 0).</td>
</tr>
<tr>
<td>D1</td>
<td>Constant Bit Rate (CBR) (H.264 low_delay_hrd_flag = 0). </td>
</tr>
<tr>
<td>D2</td>
<td>Constant QP.</td>
</tr>
<tr>
<td>D3</td>
<td>Global VBR without underflow (H.264 low_delay_hrd_flag = 0).</td>
</tr>
<tr>
<td>D4</td>
<td>VBR with underflow allowed (H.264 low_delay_hrd_flag = 1).</td>
</tr>
<tr>
<td>D5</td>
<td>Global VBR with underflow allowed (H.264 low_delay_hrd_flag = 1).</td>
</tr>
</table>
 


### -field wMaxMBperSecOneResolutionNoScalability

 


### -field wMaxMBperSecTwoResolutionsNoScalability

 


### -field wMaxMBperSecThreeResolutionsNoScalability

 


### -field wMaxMBperSecFourResolutionsNoScalability

 


### -field wMaxMBperSecOneResolutionTemporalScalability

 


### -field wMaxMBperSecTwoResolutionsTemporalScalablility

 


### -field wMaxMBperSecThreeResolutionsTemporalScalability

 


### -field wMaxMBperSecFourResolutionsTemporalScalability

 


### -field wMaxMBperSecOneResolutionTemporalQualityScalability

 


### -field wMaxMBperSecTwoResolutionsTemporalQualityScalability

 


### -field wMaxMBperSecThreeResolutionsTemporalQualityScalablity

 


### -field wMaxMBperSecFourResolutionsTemporalQualityScalability

 


### -field wMaxMBperSecOneResolutionTemporalSpatialScalability

 


### -field wMaxMBperSecTwoResolutionsTemporalSpatialScalability

 


### -field wMaxMBperSecThreeResolutionsTemporalSpatialScalablity

 


### -field wMaxMBperSecFourResolutionsTemporalSpatialScalability

 


### -field wMaxMBperSecOneResolutionFullScalability

 


### -field wMaxMBperSecTwoResolutionsFullScalability

 


### -field wMaxMBperSecThreeResolutionsFullScalability

 


### -field wMaxMBperSecFourResolutionsFullScalability

 




#### - bDynamicResolutionScaling

Defines the bitmap that specifies the synchronization frame types.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>D0</td>
<td>Instantaneous Decoding Refresh (IDR) frame with Sequence Parameter Set (SPS)  and Picture Parameter Set (PPS) headers.</td>
</tr>
<tr>
<td>D1</td>
<td>IDR frame (with SPS and PPS headers) that is a long term reference frame.</td>
</tr>
<tr>
<td>D2</td>
<td>Random-access I frame (with SPS and PPS headers), which may or may not be an IDR frame.</td>
</tr>
<tr>
<td>D3</td>
<td>P frame that is a long term reference frame.</td>
</tr>
<tr>
<td>D7-D4</td>
<td>Reserved; set to 0.</td>
</tr>
</table>
 


#### - dwMaxMBperSecFourResolutionsFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of four different resolutions.


#### - dwMaxMBperSecFourResolutionsNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable AVC streams, summing up across all layers when all layers consist of four different resolutions.


#### - dwMaxMBperSecFourResolutionsTemporalQualityScalability

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers consist of four different resolutions.


#### - dwMaxMBperSecFourResolutionsTemporalScalability

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers consist of four different resolutions.


#### - dwMaxMBperSecOneResolutionFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers have the same resolution.


#### - dwMaxMBperSecOneResolutionNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable Advanced Video Coding (AVC) streams, summing up across all layers when all layers have the same resolution.


#### - dwMaxMBperSecOneResolutionTemporalQualityScalability

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers have the same resolution.


#### - dwMaxMBperSecOneResolutionTemporalScalability

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers have the same resolution.


#### - dwMaxMBperSecThreeResolutionsFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of three different resolutions.


#### - dwMaxMBperSecThreeResolutionsNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable AVC streams, summing up across all layers when all layers consist of three different resolutions.


#### - dwMaxMBperSecThreeResolutionsTemporalQualityScalablity

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers consist of three different resolutions.


#### - dwMaxMBperSecThreeResolutionsTemporalScalability

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers consist of three different resolutions.


#### - dwMaxMBperSecTwoResolutionsFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of two different resolutions.


#### - dwMaxMBperSecTwoResolutionsNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable AVC streams, summing up across all layers when all layers consist of two different resolutions.


#### - dwMaxMBperSecTwoResolutionsTemporalQualityScalability

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers consist of two different resolutions.


#### - dwMaxMBperSecTwoResolutionsTemporalScalablility

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers consist of two different resolutions.


## -remarks



The KS_H264VIDEOINFO structure contains the frame and the format descriptor information.  




## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_datarange_h264_video.md">KS_DATARANGE_H264_VIDEO</a>



<a href="..\ksmedia\ns-ksmedia-tagks_dataformat_h264videoinfo.md">KS_DATAFORMAT_H264VIDEOINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_H264VIDEOINFO structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

