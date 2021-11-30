---
UID: NS:d3dkmdt._DXGKMDT_OPM_OMAC
title: DXGKMDT_OPM_OMAC (d3dkmdt.h)
description: The DXGKMDT_OPM_OMAC structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity.
old-location: display\dxgkmdt_opm_omac.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGKMDT_OPM_OMAC structure"]
ms.keywords: "*PDXGKMDT_OPM_OMAC, DXGKMDT_OPM_OMAC, DXGKMDT_OPM_OMAC structure [Display Devices], DmStructs_8c3b7364-5055-4152-b7ed-4e2d1d910dd4.xml, PDXGKMDT_OPM_OMAC, PDXGKMDT_OPM_OMAC structure pointer [Display Devices], _DXGKMDT_OPM_OMAC, d3dkmdt/DXGKMDT_OPM_OMAC, d3dkmdt/PDXGKMDT_OPM_OMAC, display.dxgkmdt_opm_omac"
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: DXGKMDT_OPM_OMAC, *PDXGKMDT_OPM_OMAC
f1_keywords:
 - _DXGKMDT_OPM_OMAC
 - d3dkmdt/_DXGKMDT_OPM_OMAC
 - PDXGKMDT_OPM_OMAC
 - d3dkmdt/PDXGKMDT_OPM_OMAC
 - DXGKMDT_OPM_OMAC
 - d3dkmdt/DXGKMDT_OPM_OMAC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKMDT_OPM_OMAC
 - PDXGKMDT_OPM_OMAC
 - DXGKMDT_OPM_OMAC
---

# DXGKMDT_OPM_OMAC structure

## -description

The **DXGKMDT_OPM_OMAC** structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity.

## -struct-fields

### -field abOMAC

A 16-byte array that comprises the OMAC.

## -remarks

For more information about OMAC, see the [OMAC-1 algorithm](https://go.microsoft.com/fwlink/p/?linkid=70417).

The OMAC-1 parameters that OPM and COPP use are:

*E* = AES (Advanced Encryption Standard)

*t* = 128 bits

*K* = The 128-bit key that the display miniport driver receives when [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](../dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) is called.

*n* = 128 bits

For information about AES, see the [RSA Laboratories](https://www.rsa.com) website.

## -see-also

[**DXGKMDT_OPM_CONFIGURE_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md)

[**DXGKMDT_OPM_GET_INFO_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md)

[**DXGKMDT_OPM_REQUESTED_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_requested_information.md)
