---
UID: NE:d3dkmdt._DXGKMDT_OPM_STATUS
title: _DXGKMDT_OPM_STATUS (d3dkmdt.h)
description: The DXGKMDT_OPM_STATUS enumeration identifies the status of a protected output.
old-location: display\dxgkmdt_opm_status.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_STATUS enumeration"]
ms.keywords: DXGKMDT_OPM_STATUS, DXGKMDT_OPM_STATUS enumeration [Display Devices], DXGKMDT_OPM_STATUS_LINK_LOST, DXGKMDT_OPM_STATUS_NORMAL, DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED, DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED, DXGKMDT_OPM_STATUS_TAMPERING_DETECTED, DmEnums_77faebe8-d3a4-461f-9f03-daa2d81da828.xml, _DXGKMDT_OPM_STATUS, d3dkmdt/DXGKMDT_OPM_STATUS, d3dkmdt/DXGKMDT_OPM_STATUS_LINK_LOST, d3dkmdt/DXGKMDT_OPM_STATUS_NORMAL, d3dkmdt/DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED, d3dkmdt/DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED, d3dkmdt/DXGKMDT_OPM_STATUS_TAMPERING_DETECTED, display.dxgkmdt_opm_status
req.header: d3dkmdt.h
req.include-header:
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
req.typenames: DXGKMDT_OPM_STATUS
f1_keywords:
 - _DXGKMDT_OPM_STATUS
 - d3dkmdt/_DXGKMDT_OPM_STATUS
 - DXGKMDT_OPM_STATUS
 - d3dkmdt/DXGKMDT_OPM_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DXGKMDT_OPM_STATUS
---

# _DXGKMDT_OPM_STATUS enumeration


## -description

The DXGKMDT_OPM_STATUS enumeration identifies the status of a protected output.

## -enum-fields

### -field DXGKMDT_OPM_STATUS_NORMAL

Indicates that the protected output is working correctly.

### -field DXGKMDT_OPM_STATUS_LINK_LOST

Indicates that although the protected output detected no tampering, an output protection technology unexpectedly stopped working. 

This status bit must be set if DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED is also set.

### -field DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED

Indicates that the end user caused the configuration of the physical connector to change. Therefore, a renegotiation is required.

### -field DXGKMDT_OPM_STATUS_TAMPERING_DETECTED

Indicates that tampering with the graphics adapter or the adapter's display miniport driver has occurred.

### -field DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED

Indicates that a revoked High-bandwidth Digital Content Protection (HDCP) device is directly or indirectly attached to a protected output. If HDCP is not enabled, the protected output is not required to detect revoked devices. If HDCP is enabled, the protected output must detect revoked devices. The driver sets this status value only from a call to its <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> function to determine if HDCP is enabled.

## -remarks

The display miniport driver returns status about a protected output whenever the driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> and <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a> functions are called to retrieve information about the protected output. For more information about returning a protected output's status, see <a href="/windows-hardware/drivers/display/reporting-status-of-a-protected-output">Reporting Status about a Protected Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_actual_output_format">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>
