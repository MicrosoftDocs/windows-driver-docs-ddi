---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
title: "_DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the DxgkDdiOPMConfigureProtectedOutput function.
old-location: display\dxgkmdt_opm_set_protection_level_parameters.htm
old-project: display
ms.assetid: e5b35b0d-c7ad-4a67-8552-13df4c9c2b84
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure [Display Devices], DmStructs_9d43af01-039a-4f68-8583-b42ae54a5bbe.xml, _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, d3dkmdt/DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, display.dxgkmdt_opm_set_protection_level_parameters
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
---

# _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure


## -description


The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the <a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a> function.


## -struct-fields




### -field ulProtectionType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560898">DXGKMDT_OPM_PROTECTION_TYPE</a>-typed value that indicates the protection type to set a protection level for. 


### -field ulProtectionLevel

A value that specifies the protection level to set for one of the following protection types that is specified in the <b>ulProtectionType</b> member:  





#### DXGKMDT_OPM_PROTECTION_TYPE_ACP

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560834">DXGKMDT_OPM_ACP_PROTECTION_LEVEL</a>-typed value that identifies the Analog Copy Protection (ACP) level that the protected output uses.



#### DXGKMDT_OPM_PROTECTION_TYPE_CGMSA

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560846">DXGKMDT_OPM_CGMSA</a>-typed value that identifies the Content Generation Management System Analog (CGMS-A) protection level that the protected output uses.



#### DXGKMDT_OPM_PROTECTION_TYPE_HDCP or DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560878">DXGKMDT_OPM_HDCP_PROTECTION_LEVEL</a>-typed value that identifies the High-bandwidth Digital Content Protection (HDCP) level that the protected output uses. Protected outputs with COPP semantics can use only DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP; protected outputs with OPM semantics can use only DXGKMDT_OPM_PROTECTION_TYPE_HDCP. 



#### DXGKMDT_OPM_PROTECTION_TYPE_DPCP

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560861">DXGKMDT_OPM_DPCP_PROTECTION_LEVEL</a>-typed value that identifies the DisplayPort Copy Protection (DPCP) protection level that the protected output uses.


### -field Reserved

Reserved. Must be set to zero. 


### -field Reserved2

Reserved. Must be set to zero. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560834">DXGKMDT_OPM_ACP_PROTECTION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560846">DXGKMDT_OPM_CGMSA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560861">DXGKMDT_OPM_DPCP_PROTECTION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560878">DXGKMDT_OPM_HDCP_PROTECTION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560898">DXGKMDT_OPM_PROTECTION_TYPE</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

