---
UID: NS:d3dkmddi._DXGK_SET_TIMING_PATH_INFO
title: _DXGK_SET_TIMING_PATH_INFO (d3dkmddi.h)
description: Structure to hold information to modify SetTiming path.
old-location: display\dxgk_set_timing_path_info.htm
ms.assetid: 23B42F75-6313-430F-8CD3-EBAAE87C7815
ms.date: 05/10/2018
keywords: ["DXGK_SET_TIMING_PATH_INFO structure"]
ms.keywords: DXGK_SET_TIMING_PATH_INFO, DXGK_SET_TIMING_PATH_INFO structure [Display Devices], PDXGK_SET_TIMING_PATH_INFO, PDXGK_SET_TIMING_PATH_INFO structure pointer [Display Devices], _DXGK_SET_TIMING_PATH_INFO, d3dkmddi/DXGK_SET_TIMING_PATH_INFO, d3dkmddi/PDXGK_SET_TIMING_PATH_INFO, display.dxgk_set_timing_path_info
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
tech.root: display
req.typenames: DXGK_SET_TIMING_PATH_INFO
ms.custom: 19H1
f1_keywords:
 - _DXGK_SET_TIMING_PATH_INFO
 - d3dkmddi/_DXGK_SET_TIMING_PATH_INFO
 - DXGK_SET_TIMING_PATH_INFO
 - d3dkmddi/DXGK_SET_TIMING_PATH_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_SET_TIMING_PATH_INFO
dev_langs:
 - c++
---

# _DXGK_SET_TIMING_PATH_INFO structure


## -description

Structure to hold information to modify SetTiming path.

## -struct-fields

### -field VidPnTargetId

The identifier of a display adapter's video present target.

The following members are embedded in a union:

#### OutputColorSpace

A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a> value which describes the output color space intended for the transported pixels.  The driver is responsible for sending appropriate metadata to ensure the display device is set up to interpret pixels correctly for this color space. 

The output colorspace is fixed until modified by another SetTiming call.  If the colorspace set on swap chain presented to this target is different from the output colorspace, the driver is required to convert to the output colorspace during scan-out.  

If multiple pixel planes are enabled on the target, the driver must perform composition of the planes in a valid composition colorspace, typically a linear space in addition to converting the composed pixels into the output colorspace. 

Since the SelectedWireFormat already indicates the color encoding, and chroma subsampling, the OutputColorSpace is only used to determine the primaries and gamma with which the pixel values should be encoded; the other elements: color model, range and cositing should be ignored as they are defined by the SelectedWireFormat.
Given that there are no plans to support ST.2084 gamma with Rec.709 primaries, or 2.2 gamma with Rec 2020 primaries, the result is that only two values are ever set by the OS in the RS2 release which are: 

<dl>
<dd>D3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P709, for SDR
</dd>
<dd>D3DDDI_COLOR_SPACE_RGB_FULL_G2084_NONE_P2020, for HDR10
</dd>
</dl>



#### OutputWireColorSpace

The D3DDDI_COLOR_SPACE_TYPE enum type is also used by OS to specify the input color space of MPOs, hence it is deprecated starting in WDDM 2.3. WDDM2.3 and later drivers should use the new type D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE.

### -field SelectedWireFormat

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_wire_format_and_preference.md">D3DKMDT_WIRE_FORMAT_AND_PREFERENCE</a> value which indicates the wire format to be set for the path. The Preference field is reserved in this context so should be ignored by the driver.  In the remaining five bit-fields, the OS will set one of the thirty bits to indicate which color encoding and at which bit depth the link should be driven.

#### Input

The following members are embedded in an Input union:


#### VidPnPathUpdates

Describes how the VidPn elements corresponding to this path have been changed since the previous successful call.

Fields in the DXGK_SET_TIMING_PATH_INFO structure are excluded from this summary so the driver always needs to evaluate these fields for any changes.
For example, if the OS calls SetTimings to idle the monitor on a path, the Active flag would be cleared and the VidPnPathUpdates will be set to DXGK_PATH_UPDATE_UNMODIFIED, if it then calls SetTimings to power up the monitor, the Active flag would be set and the VidPnPathUpdates will still be set to DXGK_PATH_UPDATE_UNMODIFIED.


#### Active

If set, indicates that the path should be activated or remain active.
If clear, indicates that the path should be deactivated or remain inactive.



#### IgnoreConnectivity

If set, indicates that the driver should force output to the target even though no display device has been detected.
If clear, the driver should report an updated ConnectionStatus if the connectivity has changed.



#### PreserveInherited

If set, indicates that the driver should preserve the timings and content which were configured by a previous driver.  This flag is only used when the adapter was configured by something other than the current instance of the driver.  Initially, this will be used when the path was initialized by firmware during boot.
If clear, no special behavior is requested.


#### SyncLockGroup

Sync lock group input. Available starting in WDDM 2.4.
Indicates which group of synchronized displays each path belongs to. Since WDDM 2.4 - WDDM 2.6 only support a single sync group per adapter and always enables synchronization when possible, this value is set to 1 when sync-able displays are enabled, and 0 when the display is not required to be synchronized and should always be paired with *SyncLockStyle* of value DXGK_SYNC_LOCK_STYLE_NONE.

#### SyncLockStyle

Sync lock style input. Available starting in WDDM 2.4.
Indicates what style of synchronization the OS is requesting. For a WDDM 2.4 - WDDM 2.6 driver, this value is set to [DXGK_SYNC_LOCK_STYLE_IDENTICAL](ne-d3dkmddi-_dxgk_sync_lock_style.md) if sync-able displays are enabled and DXGK_SYNC_LOCK_STYLE_NONE otherwise.

#### Reserved

This value is reserved for system use.


#### InputFlags

A set of flags specifying what the OS wants the driver to do.

#### Output

The following members are embedded in an Output union:

#### RecheckMPO

If set, indicates that the OS needs to issue a CheckMPO due to changes on this path.

#### Reserved

This value is reserved for system use.

#### OutputFlags

A set of flags specifying outcomes the OS needs to be aware of relating to this path.

### -field TargetState

Indicates the target state as a result of this call. Since changing timings may cause the connection state of both modified targets and targets which the OS did not intended to change, this field communicates the state for each path.

If the target state is unchanged, this field should contain a copy of the last state reported on the target, including the same ConnectionChangeId which was previously reported.

If the target state is changed, this field should contain a copy of the queued, connection change which reflects the state resulting from the SetTiming call.

The following members are embedded in a union:

#### GlitchCause

A DXGK_GLITCH_CAUSE value which indicates which underlying change(s) in the display pipeline caused the glitch.


#### GlitchEffect

A DXGK_GLITCH_EFFECT value which indicates how the glitch was presented to the user.


#### GlitchDuration

A DXGK_GLITCH_DURATION value which indicates approximately how long the glitch lasted.

<div class="alert"><b>Note</b>  This is intended to reflect how long the underlying issue was present, but the visible effect may be longer in some cases.  For example, when sync is lost long enough for a monitor to have to re-detect, the display device will likely take many frames to recover.  It is the length of the underlying issue which should be reported, not the recovery time as that will vary between devices</div>
<div> </div>

#### Reserved

This value is reserved for system use.


#### DiagnosticInfo

Set of information filled out by the driver for each path to describe any side-effects of the timing change.
In many cases, glitches are inevitable so these fields attempt to understand the underlying cause and the extent of user impact.

## -syntax

```cpp
typedef struct _DXGK_SET_TIMING_PATH_INFO {
  D3DDDI_VIDEO_PRESENT_TARGET_ID     VidPnTargetId;
  D3DDDI_COLOR_SPACE_TYPE            OutputColorSpace;
  D3DKMDT_WIRE_FORMAT_AND_PREFERENCE SelectedWireFormat;
  union {
    struct {
      DXGK_PATH_UPDATE VidPnPathUpdates  :2;
      UINT             Active  :1;
      UINT             IgnoreConnectivity  :1;
      UINT             PreserveInherited  :1;
      UINT             Reserved  :27;
    } Input;
    UINT InputFlags;
  };
  union {
    struct {
      UINT RecheckMPO  :1;
      UINT Reserved  :31;
    } Output;
    UINT OutputFlags;
  };
  DXGK_CONNECTION_CHANGE             TargetState;
  union {
    struct {
      DXGK_GLITCH_CAUSE    GlitchCause;
      DXGK_GLITCH_EFFECT   GlitchEffect;
      DXGK_GLITCH_DURATION GlitchDuration;
      UINT8                Reserved;
    };
    UINT DiagnosticInfo;
  };
} DXGK_SET_TIMING_PATH_INFO, *PDXGK_SET_TIMING_PATH_INFO;
```