---
UID: NE:d3dkmthk._D3DKMT_ESCAPETYPE
title: D3DKMT_ESCAPETYPE (d3dkmthk.h)
description: Learn more about the D3DKMT_ESCAPETYPE enumeration.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DKMT_ESCAPETYPE
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_ESCAPETYPE
 - d3dkmthk/_D3DKMT_ESCAPETYPE
 - D3DKMT_ESCAPETYPE
 - d3dkmthk/D3DKMT_ESCAPETYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ESCAPETYPE
 - D3DKMT_ESCAPETYPE
---

# D3DKMT_ESCAPETYPE enumeration

## -description

The **D3DKMT_ESCAPETYPE** enumeration specifies the type of escape operation to perform.

## -enum-fields

### -field D3DKMT_ESCAPE_DRIVERPRIVATE

The escape operation and data are private between the user-mode display driver (UMD) (or client driver) and the kernel-mode display miniport driver (KMD). The hardware vendor defines the format of the data.

### -field D3DKMT_ESCAPE_VIDMM

For internal testing purposes only.

### -field D3DKMT_ESCAPE_TDRDBGCTRL

For internal testing purposes only.

### -field D3DKMT_ESCAPE_VIDSCH

For internal testing purposes only.

### -field D3DKMT_ESCAPE_DEVICE

For internal testing purposes only.

### -field D3DKMT_ESCAPE_DMM

For internal testing purposes only.

### -field D3DKMT_ESCAPE_DEBUG_SNAPSHOT

For internal testing purposes only.

### -field D3DKMT_ESCAPE_DRT_TEST

For internal testing purposes only.

### -field D3DKMT_ESCAPE_DIAGNOSTICS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT

For internal testing purposes only.

### -field D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_BDD_PNP

For internal testing purposes only.

### -field D3DKMT_ESCAPE_BDD_FALLBACK

For internal testing purposes only.

### -field D3DKMT_ESCAPE_ACTIVATE_SPECIFIC_DIAG

For internal testing purposes only.

### -field D3DKMT_ESCAPE_MODES_PRUNED_OUT

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WHQL_INFO

For internal testing purposes only.

### -field D3DKMT_ESCAPE_BRIGHTNESS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_EDID_CACHE

For internal testing purposes only.

### -field D3DKMT_ESCAPE_MIRACAST_DISPLAY_REQUEST

For internal testing purposes only.

### -field D3DKMT_ESCAPE_HISTORY_BUFFER_STATUS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_MIRACAST_ADAPTER_DIAG_INFO

For internal testing purposes only.

### -field D3DKMT_ESCAPE_FORCE_BDDFALLBACK_HEADLESS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_REQUEST_MACHINE_CRASH

For internal testing purposes only.

### -field D3DKMT_ESCAPE_SOFTGPU_ENABLE_DISABLE_HMD

For internal testing purposes only.

### -field D3DKMT_ESCAPE_PROCESS_VERIFIER_OPTION

For internal testing purposes only.

### -field D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION

For internal testing purposes only.

### -field D3DKMT_ESCAPE_IDD_REQUEST

For internal testing purposes only.

### -field D3DKMT_ESCAPE_DOD_SET_DIRTYRECT_MODE

For internal testing purposes only.

### -field D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET

For internal testing purposes only.

### -field D3DKMT_ESCAPE_LOG_USERMODE_DAIG_PACKET

For internal testing purposes only.

### -field D3DKMT_ESCAPE_GET_EXTERNAL_DIAGNOSTICS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_GET_DISPLAY_CONFIGURATIONS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_QUERY_IOMMU_STATUS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_START

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_HIP_DEVICE_INFO

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_QUERY_CD_ROTATION_BLOCK

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_DPI_INFO

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_PRESENTER_VIEW_INFO

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_SYSTEM_DPI

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_BDD_FALLBACK

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_DDA_TEST_CTL

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_USER_DETECTED_BLACK_SCREEN

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_DISPBROKER_TEST

For internal testing purposes only.

### -field D3DKMT_ESCAPE_CCD_DATABASE

For internal testing purposes only.

### -field D3DKMT_ESCAPE_QUERY_DMA_REMAPPING_STATUS

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_COLOR_PROFILE_INFO

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_SET_DIMMED_STATE

For internal testing purposes only.

### -field D3DKMT_ESCAPE_WIN32K_SPECIALIZED_DISPLAY_TEST

For internal testing purposes only.

## -see-also

[**D3DKMT_ESCAPE**](ns-d3dkmthk-_d3dkmt_escape.md)

[**D3DKMTEscape**](nf-d3dkmthk-d3dkmtescape.md)
