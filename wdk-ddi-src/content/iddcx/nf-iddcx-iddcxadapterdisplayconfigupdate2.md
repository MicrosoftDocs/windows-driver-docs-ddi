---
UID: NF:iddcx.IddCxAdapterDisplayConfigUpdate2
tech.root: display
title: IddCxAdapterDisplayConfigUpdate2
ms.date: 09/22/2023
targetos: Windows
description: Learn about the IddCxAdapterDisplayConfigUpdate2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxAdapterDisplayConfigUpdate2
f1_keywords:
 - IddCxAdapterDisplayConfigUpdate2
 - iddcx/IddCxAdapterDisplayConfigUpdate2
dev_langs:
 - c++
helpviewer_keywords:
 - IddCxAdapterDisplayConfigUpdate2
---

## -description

A remote driver can call **IddCxAdapterDisplayConfigUpdate2** to allow a client to tell the server how to update the monitor configuration.

## -parameters

### -param AdapterObject

[in] The [**IDDCX_ADAPTER**](/windows-hardware/drivers/display/iddcx-objects) object of the remote adapter that the display configuration is specified for.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md) structure containing input arguments to the function.

## -returns

**IddCxAdapterDisplayConfigUpdate2** returns STATUS_SUCCESS upon success; otherwise, it returns an appropriate error code.

## -remarks

A remote indirect display driver can call **IddCxAdapterDisplayConfigUpdate2** to set the mode, colorimetry and other values that the OS should use for a specific monitor. Only remote drivers are able to call this function.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

The [**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md) structure is defined in such a way that not all information has to be provided in every call. For example, some paths may not supply colorimetry data if the color mode is not HDR or WCG, or **IddCxAdapterDisplayConfigUpdate2** could be called to only update the SDR white level if no layout changes are required.

Controlling modes (setting the [**IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID**](ne-iddcx-iddcx_displayconfigpath2_flags.md) flag for a path) has some additional rules and clarifications:

* If any path has **IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID** set then all paths provided must have it set
* When **IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID** is provided on all paths then any currently active paths not in the path list will become inactive
* If only non-**IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID** flags are set then only the paths to be updated need to be present
* Depending on the color mode specified, additional data may be required for a path. The following table indicates what additional flags must be set:

| Color mode | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_COLORIMETRY_VALID | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_SDRWHITELEVEL_VALID |
|------------|----------------------------------------------------------|------------------------------------------------------------|
| SDR        | No                                                       | No              |
| SDRWCG     | Yes                                                      | No              |
| HDR        | Yes                                                      | Yes             |

### First versus subsequent calls to IddCxAdapterDisplayConfigUpdate2

The first time a path is included in a **IddCxAdapterDisplayConfigUpdate2** call has different requirements than subsequent times. The following table outlines the requirements.

| Path field      | Required in initial call for path | Can be updated after initial call | How would Windows client get the info|
| ----------------|-----------------------------------|-----------------------------------|--------------------------------------|
| Mode            | Yes                               | Yes                               | [**QueryDisplayConfig**](/windows/win32/api/winuser/nf-winuser-querydisplayconfig) will provide client display configuration and [**WM_DISPLAYCHANGE**](/windows/win32/gdi/wm-displaychange) is sent when display config changes; [**AdvancedColorInfo.CurrentAdvancedColorKind**](/uwp/api/windows.graphics.display.advancedcolorinfo.currentadvancedcolorkind) will give a color mode |
| Scale factor    | Yes                               | Yes                               | Drivers can use the method used for [**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md) |
| Physical size   | Yes if no EDID passed             | No                                | Not needed if EDID passed |
| Colorimetry     | Yes for non SDR color mode        | Yes                               | Most fields from corresponding **AdvancedColorInfo** fields |
| SDR white level | Yes for HDR color mode, default is 80 nits | Yes                      | **AdvancedColorInfo.SdrWhiteLevelInNits**, see [DirectX with Advanced Color on HDR/SDR displays](/windows/win32/direct3darticles/high-dynamic-range) for more information |

### Behavior differences when running on Windows 11, version 22H2 September Update

Due to underlying OS functionality, the support for drivers requesting HDR and WCG color modes when running on Windows 11, version 22H2 September Update differs slightly from when running on the Windows platform release coming in 2024. A driver can use the [**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md) function to determine which OS they are running on. The following table describes which color modes a driver can request depending on the monitor descriptor previously provided to the OS:

| Edid type | 22H2 September Update possible color modes | Platform release in 2024 possible color modes |
|-----------|--------------------------------|-------------------------|
| None      | SDR, HDR                       | SDR, SDRWCG, HDR        |
| SDR       | SDR, SDRWCG                    | SDR, SDRWCG             |
| HDR       | SDR, HDR                       | SDR, SDRWCG, HDR        |

### Examples

Some examples of which paths to include in subsequent **IddCxAdapterDisplayConfigUpdate2** calls follow. At the start of each scenario, a remote session has the following paths configured:  

| Monitor | Resolution       | Desktop position | Color mode |
|---------|------------------|------------------|------------|
|       1 | 1920x1080 @ 30Hz |              0,0 | SDR        |
|       2 |  1024x768 @ 30Hz |           1024,0 | SDRWCG     |
|       3 | 3840x2160 @ 30Hz |           0,1848 | HDR        |  

#### Scenario 1 - Change the desktop position of Monitor 3 to be left of Monitor 1

| Monitor | Flags                                     | Details |
|---------|-------------------------------------------|---------|
|       1 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |
|       2 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |
|       3 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | Change the desktop position to -3840,0 |

#### Scenario 2 – Change monitor 2 from SDRWCG to SDR

| Monitor | Flags                                     | Details |
|---------|-------------------------------------------|---------|
|       1 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |
|       2 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | Set new color mode |
|       3 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |

#### Scenario 3 – Change monitor 1 from SDR to HDR

| Monitor | Flags                                     | Details |
|---------|-------------------------------------------|---------|
|       1 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID, IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_COLORIMETRY_VALID, IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_SDRWHITELEVEL_VALID | Set new color mode, colorimetry and SDR white level |
|       2 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |
|       3 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |

#### Scenario 4 – Change scale factor of Monitor 2

| Monitor | Flags                                     | Details |
|---------|-------------------------------------------|---------|
|       2 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_SCALE_FACTOR_VALID | Set new scale factor |

#### Scenario 5 – Change scale factor of Monitor 2 and the desktop position of Monitor 3 to be left of Monitor 1

| Monitor | Flags                                     | Details |
|---------|-------------------------------------------|---------|
|       1 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |
|       2 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID, IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_SCALE_FACTOR_VALID | No change to current mode data, set new scale factor |
|       3 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | Change the desktop position to -3840,0 |

#### Scenario 6 – Remove Monitor 2 from the current configuration

| Monitor | Flags                                     | Details |
|---------|-------------------------------------------|---------|
|       1 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |
|       3 | IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID | No change to current mode data |

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)
