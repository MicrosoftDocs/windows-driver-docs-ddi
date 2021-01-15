---
UID: NC:dispmprt.DXGKDDI_OPM_GET_CERTIFICATE_SIZE
title: DXGKDDI_OPM_GET_CERTIFICATE_SIZE (dispmprt.h)
description: The DxgkDdiOPMGetCertificateSize function retrieves the size of a certificate of the given type.
old-location: display\dxgkddiopmgetcertificatesize.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback function"]
ms.keywords: DXGKDDI_OPM_GET_CERTIFICATE_SIZE, DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback, Dm_Opm_functions_62785ff7-3c52-4e07-b075-eb27de1236b8.xml, DxgkDdiOPMGetCertificateSize, DxgkDdiOPMGetCertificateSize callback function [Display Devices], display.dxgkddiopmgetcertificatesize, dispmprt/DxgkDdiOPMGetCertificateSize
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_OPM_GET_CERTIFICATE_SIZE
 - dispmprt/DXGKDDI_OPM_GET_CERTIFICATE_SIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_OPM_GET_CERTIFICATE_SIZE
---

# DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback function


## -description

The<i> DxgkDdiOPMGetCertificateSize</i> function retrieves the size of a certificate of the given type.

## -parameters

### -param MiniportDeviceContext 

[in]
A handle to a context block that is associated with a display adapter. Previously, the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.

### -param CertificateType 

[in]
A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_certificate_type">DXGKMDT_CERTIFICATE_TYPE</a>-typed value that identifies the type of certificate whose size <i> DxgkDdiOPMGetCertificateSize</i>  returns.

### -param CertificateSize 

[out]
A pointer to a variable that receives the size, in bytes, of the certificate whose type is identified by the value in the <i>CertificateType</i> parameter.

## -returns

<i>DxgkDdiOPMGetCertificateSize</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully retrieved the certificate size.|
|STATUS_GRAPHICS_OPM_NOT_SUPPORTED|The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. DxgkDdiOPMGetCertificateSize can also return this value if the display miniport driver detected tampering.|
|STATUS_GRAPHICS_COPP_NOT_SUPPORTED|The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. DxgkDdiOPMGetCertificateSize can also return this value if the miniport driver detected tampering.|
|STATUS_GRAPHICS_UAB_NOT_SUPPORTED|The display miniport driver does not support UAB either because the hardware vender never signed the UAB license agreement or the miniport driver's graphics hardware does not comply with UAB rules. DxgkDdiOPMGetCertificateSize can also return this value if the display miniport driver detected tampering.|
|STATUS_GRAPHICS_PVP_HFS_FAILED|The display miniport driver's hardware functionality scan (HFS) failed or the display miniport driver detected tampering. A display miniport driver can optionally return this value. If DxgkDdiOPMGetCertificateSize does not return this value for tampering, it can return one of the previous error codes instead.|

This function might also return other error codes that are defined in Ntstatus.h.

## -remarks

<i>DxgkDdiOPMGetCertificateSize</i> can retrieve the size of the display miniport driver's OPM certificate, User Accessible Bus (UAB) certificate, or Certified Output Protection Protocol (COPP) certificate. For information about these certificates, download the Output Content Protection document from the <a href="https://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.

<i>DxgkDdiOPMGetCertificateSize</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_certificate_type">DXGKMDT_CERTIFICATE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

