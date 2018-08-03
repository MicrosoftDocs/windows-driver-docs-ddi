---
UID: NC:dispmprt.DXGKDDI_OPM_GET_CERTIFICATE_SIZE
title: DXGKDDI_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: The DxgkDdiOPMGetCertificateSize function retrieves the size of a certificate of the given type.
old-location: display\dxgkddiopmgetcertificatesize.htm
tech.root: display
ms.assetid: fe4197ad-52a2-47b3-ad96-57ea73cd931f
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_OPM_GET_CERTIFICATE_SIZE, DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback, Dm_Opm_functions_62785ff7-3c52-4e07-b075-eb27de1236b8.xml, DxgkDdiOPMGetCertificateSize, DxgkDdiOPMGetCertificateSize callback function [Display Devices], display.dxgkddiopmgetcertificatesize, dispmprt/DxgkDdiOPMGetCertificateSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiOPMGetCertificateSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback function


## -description


The<i> DxgkDdiOPMGetCertificateSize</i> function retrieves the size of a certificate of the given type.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. Previously, the display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param CertificateType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560826">DXGKMDT_CERTIFICATE_TYPE</a>-typed value that identifies the type of certificate whose size <i> DxgkDdiOPMGetCertificateSize</i>  returns.


### -param CertificateSize [out]

A pointer to a variable that receives the size, in bytes, of the certificate whose type is identified by the value in the <i>CertificateType</i> parameter.


## -returns



<i>DxgkDdiOPMGetCertificateSize</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function successfully retrieved the certificate size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_OPM_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. <i>DxgkDdiOPMGetCertificateSize</i> can also return this value if the display miniport driver detected tampering. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_COPP_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. <i>DxgkDdiOPMGetCertificateSize</i> can also return this value if the miniport driver detected tampering. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_UAB_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support UAB either because the hardware vender never signed the UAB license agreement or the miniport driver's graphics hardware does not comply with UAB rules. <i>DxgkDdiOPMGetCertificateSize</i> can also return this value if the display miniport driver detected tampering. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_PVP_HFS_FAILED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver's hardware functionality scan (HFS) failed or the display miniport driver detected tampering. A display miniport driver can optionally return this value. If <i>DxgkDdiOPMGetCertificateSize</i> does not return this value for tampering, it can return one of the previous error codes instead. 

</td>
</tr>
</table>
 

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



<i>DxgkDdiOPMGetCertificateSize</i> can retrieve the size of the display miniport driver's OPM certificate, User Accessible Bus (UAB) certificate, or Certified Output Protection Protocol (COPP) certificate. For information about these certificates, download the Output Content Protection document from the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.

<i>DxgkDdiOPMGetCertificateSize</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560826">DXGKMDT_CERTIFICATE_TYPE</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

