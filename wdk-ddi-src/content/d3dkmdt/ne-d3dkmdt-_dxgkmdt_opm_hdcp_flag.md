---
UID: NE:d3dkmdt._DXGKMDT_OPM_HDCP_FLAG
title: _DXGKMDT_OPM_HDCP_FLAG (d3dkmdt.h)
description: The DXGKMDT_OPM_HDCP_FLAG enumeration identifies whether a protected output's physical connector is connected to a High-bandwidth Digital Content Protection (HDCP) repeater.
old-location: display\dxgkmdt_opm_hdcp_flag.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_HDCP_FLAG enumeration"]
ms.keywords: DXGKMDT_OPM_HDCP_FLAG, DXGKMDT_OPM_HDCP_FLAG enumeration [Display Devices], DXGKMDT_OPM_HDCP_FLAG_NONE, DXGKMDT_OPM_HDCP_FLAG_REPEATER, DmEnums_4969beac-7f4f-4bef-bd67-65599816c9ee.xml, _DXGKMDT_OPM_HDCP_FLAG, d3dkmdt/DXGKMDT_OPM_HDCP_FLAG, d3dkmdt/DXGKMDT_OPM_HDCP_FLAG_NONE, d3dkmdt/DXGKMDT_OPM_HDCP_FLAG_REPEATER, display.dxgkmdt_opm_hdcp_flag
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
req.typenames: DXGKMDT_OPM_HDCP_FLAG
f1_keywords:
 - _DXGKMDT_OPM_HDCP_FLAG
 - d3dkmdt/_DXGKMDT_OPM_HDCP_FLAG
 - DXGKMDT_OPM_HDCP_FLAG
 - d3dkmdt/DXGKMDT_OPM_HDCP_FLAG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKMDT_OPM_HDCP_FLAG
 - DXGKMDT_OPM_HDCP_FLAG
---

# _DXGKMDT_OPM_HDCP_FLAG enumeration


## -description

The DXGKMDT_OPM_HDCP_FLAG enumeration identifies whether a protected output's physical connector is connected to a High-bandwidth Digital Content Protection (HDCP) repeater.

## -enum-fields

### -field DXGKMDT_OPM_HDCP_FLAG_NONE

Indicates that no HDCP flags are set. Therefore, the protected output's physical connector is not connected to an HDCP repeater.

### -field DXGKMDT_OPM_HDCP_FLAG_REPEATER

Indicates that the protected output's physical connector is connected to an HDCP repeater.

## -remarks

The DXGKMDT_OPM_HDCP_FLAG enumeration is used only if a protected output has Certified Output Protection Protocol (COPP) semantics. 

An HDCP repeater is a device that allows multiple monitors to display the video signal from a protected output's physical connector. For example, if a user connected an HDCP repeater from a graphics adapter's Digital Video Interface (DVI) connector to a TV monitor and computer monitor, both monitors would display the same picture. For more information about HDCP repeaters, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>

