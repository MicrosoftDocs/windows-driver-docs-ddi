---
UID: NC:dispmprt.DXGKDDI_OPM_GET_CERTIFICATE
title: DXGKDDI_OPM_GET_CERTIFICATE (dispmprt.h)
description: The DxgkDdiOPMGetCertificate function retrieves a certificate of the given type and size.
old-location: display\dxgkddiopmgetcertificate.htm
tech.root: display
ms.assetid: 3c055598-5f07-46e1-830d-1df9a459f742
ms.date: 05/10/2018
ms.keywords: DXGKDDI_OPM_GET_CERTIFICATE, DXGKDDI_OPM_GET_CERTIFICATE callback, Dm_Opm_functions_80d478db-b192-4d86-8938-c105bcc8a677.xml, DxgkDdiOPMGetCertificate, DxgkDdiOPMGetCertificate callback function [Display Devices], display.dxgkddiopmgetcertificate, dispmprt/DxgkDdiOPMGetCertificate
ms.topic: callback
f1_keywords:
 - "dispmprt/DxgkDdiOPMGetCertificate"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiOPMGetCertificate
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_OPM_GET_CERTIFICATE callback function


## -description


The<i> DxgkDdiOPMGetCertificate</i> function retrieves a certificate of the given type and size.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param CertificateType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ne-d3dkmdt-_dxgkmdt_certificate_type">DXGKMDT_CERTIFICATE_TYPE</a>-typed value that identifies the type of certificate to retrieve.


### -param CertificateSize [in]

The size, in bytes, of the certificate to retrieve. This size was returned by a call to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a> function.


### -param CertificateBuffer [out]

A pointer to a buffer that receives the requested certificate if <i>DxgkDdiOPMGetCertificate</i> returns successfully. If <i>DxgkDdiOPMGetCertificate</i> fails, the contents of the buffer are unchanged.


## -returns



<i>DxgkDdiOPMGetCertificate</i> returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully retrieved the certificate.|
|STATUS_GRAPHICS_OPM_NOT_SUPPORTED|The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. DxgkDdiOPMGetCertificate can also return this value if the display miniport driver detected tampering.|
|STATUS_GRAPHICS_COPP_NOT_SUPPORTED|The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. DxgkDdiOPMGetCertificate can also return this value if the display miniport driver detected tampering.|
|STATUS_GRAPHICS_UAB_NOT_SUPPORTED|The display miniport driver does not support UAB either because the hardware vender never signed the UAB license agreement or the miniport driver's graphics hardware does not comply with UAB rules. DxgkDdiOPMGetCertificate can also return this value if the display miniport driver detected tampering.|
|STATUS_GRAPHICS_PVP_HFS_FAILED|The display miniport driver's hardware functionality scan (HFS) failed or the display miniport driver detected tampering. A display miniport driver can optionally return this value. If DxgkDdiOPMGetCertificate does not return this value for tampering, it can return one of the previous error codes instead.|
 

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



<i>DxgkDdiOPMGetCertificate</i> can retrieve the display miniport driver's OPM certificate, User Accessible Bus (UAB) certificate, or Certified Output Protection Protocol (COPP) certificate. For information about these certificates, download the Output Content Protection document from the <a href="https://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.

<i>DxgkDdiOPMGetCertificate</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ne-d3dkmdt-_dxgkmdt_certificate_type">DXGKMDT_CERTIFICATE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a>
 

 

