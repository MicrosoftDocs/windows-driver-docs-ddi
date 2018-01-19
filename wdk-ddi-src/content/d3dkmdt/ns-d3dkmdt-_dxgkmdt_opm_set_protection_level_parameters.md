---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
title: _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
author: windows-driver-content
description: The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the DxgkDdiOPMConfigureProtectedOutput function.
old-location: display\dxgkmdt_opm_set_protection_level_parameters.htm
old-project: display
ms.assetid: e5b35b0d-c7ad-4a67-8552-13df4c9c2b84
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
req.alt-loc: d3dkmdt.h
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
req.typenames: DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
---

# _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure



## -description
The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function.



## -syntax

````
typedef struct _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS {
  ULONG ulProtectionType;
  ULONG ulProtectionLevel;
  ULONG Reserved;
  ULONG Reserved2;
} DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS;
````


## -struct-fields

### -field ulProtectionType

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_protection_type.md">DXGKMDT_OPM_PROTECTION_TYPE</a>-typed value that indicates the protection type to set a protection level for. 


### -field ulProtectionLevel

A value that specifies the protection level to set for one of the following protection types that is specified in the <b>ulProtectionType</b> member:  




### -field DXGKMDT_OPM_PROTECTION_TYPE_ACP

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_acp_protection_level.md">DXGKMDT_OPM_ACP_PROTECTION_LEVEL</a>-typed value that identifies the Analog Copy Protection (ACP) level that the protected output uses.


### -field DXGKMDT_OPM_PROTECTION_TYPE_CGMSA

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_cgmsa.md">DXGKMDT_OPM_CGMSA</a>-typed value that identifies the Content Generation Management System Analog (CGMS-A) protection level that the protected output uses.


### -field DXGKMDT_OPM_PROTECTION_TYPE_HDCP or DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_hdcp_protection_level.md">DXGKMDT_OPM_HDCP_PROTECTION_LEVEL</a>-typed value that identifies the High-bandwidth Digital Content Protection (HDCP) level that the protected output uses. Protected outputs with COPP semantics can use only DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP; protected outputs with OPM semantics can use only DXGKMDT_OPM_PROTECTION_TYPE_HDCP. 


### -field DXGKMDT_OPM_PROTECTION_TYPE_DPCP

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560861">DXGKMDT_OPM_DPCP_PROTECTION_LEVEL</a>-typed value that identifies the DisplayPort Copy Protection (DPCP) protection level that the protected output uses.

</dd>
</dl>

### -field Reserved

Reserved. Must be set to zero. 


### -field Reserved2

Reserved. Must be set to zero. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_acp_protection_level.md">DXGKMDT_OPM_ACP_PROTECTION_LEVEL</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_cgmsa.md">DXGKMDT_OPM_CGMSA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560861">DXGKMDT_OPM_DPCP_PROTECTION_LEVEL</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_hdcp_protection_level.md">DXGKMDT_OPM_HDCP_PROTECTION_LEVEL</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_protection_type.md">DXGKMDT_OPM_PROTECTION_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

