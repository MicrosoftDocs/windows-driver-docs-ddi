---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS
title: "_DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure contains parameters to set the version of a High-bandwidth Digital Content Protection (HDCP) System Renewability Message (SRM) for a protected output.
old-location: display\dxgkmdt_opm_set_hdcp_srm_parameters.htm
old-project: display
ms.assetid: fd069b0c-9af3-4442-aba0-1d81465e7eb0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS, DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure [Display Devices], display.dxgkmdt_opm_set_hdcp_srm_parameters, d3dkmdt/DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS, _DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS, DmStructs_6e80579a-8a17-47c0-b877-1e7712de2f04.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS
---

# _DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure


## -description


The DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure contains parameters to set the version of a High-bandwidth Digital Content Protection (HDCP) System Renewability Message (SRM) for a protected output.


## -syntax


````
typedef struct _DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS {
  ULONG ulSRMVersion;
} DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS;
````


## -struct-fields




### -field ulSRMVersion

The version number of an HDCP SRM. The least significant bits (bits 0 through 15) contain the SRM's version number in little-endian format. The SRM's version number is stored in the SRM's SRM version field in little-endian format. For more information about the SRM's SRM version field, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>. 


## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

