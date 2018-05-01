---
UID: NS:d3dkmdt._DXGKMDT_OPM_REQUESTED_INFORMATION
title: "_DXGKMDT_OPM_REQUESTED_INFORMATION"
author: windows-driver-content
description: The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the DxgkDdiOPMGetInformation or DxgkDdiOPMGetCOPPCompatibleInformation function.
old-location: display\dxgkmdt_opm_requested_information.htm
old-project: display
ms.assetid: c483786a-be8c-4ae3-a48c-45064ce81939
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PDXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION structure [Display Devices], DmStructs_671b07eb-3d44-4c06-863a-8bd74f10ee4b.xml, PDXGKMDT_OPM_REQUESTED_INFORMATION, PDXGKMDT_OPM_REQUESTED_INFORMATION structure pointer [Display Devices], _DXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/DXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/PDXGKMDT_OPM_REQUESTED_INFORMATION, display.dxgkmdt_opm_requested_information"
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
-	DXGKMDT_OPM_REQUESTED_INFORMATION
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_REQUESTED_INFORMATION, *PDXGKMDT_OPM_REQUESTED_INFORMATION
---

# _DXGKMDT_OPM_REQUESTED_INFORMATION structure


## -description


The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the <a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a> or <a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.


## -struct-fields




### -field omac

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560887">DXGKMDT_OPM_OMAC</a> structure that contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. For more information about OMAC, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70417">OMAC-1 algorithm</a>. The OMAC-1 parameters that OPM and COPP use are:

<i>E</i> = AES (Advanced Encryption Standard)

<i>t</i> = 128 bits

<i>K</i> = The 128-bit key that the display miniport driver receives when <a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> is called.

<i>n</i> = 128 bits 

For information about AES, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. 


### -field cbRequestedInformationSize

The size, in bytes, of the valid data that the <b>abRequestedInformation</b> member points to. 


### -field abRequestedInformation

A 4076-byte array that specifies the information that is retrieved from a protected output object.

To return the requested information, the display miniport driver should cast <b>abRequestedInformation</b> to one of the following structures, depending on the GUID that was specified in the <b>guidInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560868">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560859">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter of <a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a> or <a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a> points to. As an example, the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUID indicates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560854">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a> structure.

<table>
<tr>
<th>GUID</th>
<th>Structure for retrieved information</th>
</tr>
<tr>
<td>

<dl>
<dt>DXGKMDT_OPM_GET_CONNECTOR_TYPE, DXGKMDT_OPM_GET_SUPPORTED_PROTECTION_TYPES, DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ADAPTER_BUS_TYPE, </dt>
<dt>DXGKMDT_OPM_GET_DVI_CHARACTERISTICS, or DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION</dt>
</dl>


</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560925">DXGKMDT_OPM_STANDARD_INFORMATION</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_ACTUAL_OUTPUT_FORMAT

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560840">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_OUTPUT_ID

</td>
<td>
Supported in Windows 7 and later versions.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff560890">DXGKMDT_OPM_OUTPUT_ID</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560830">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_CONNECTED

_HDCP_DEVICE_INFORMATION

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560854">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>


</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560830">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560840">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560854">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560859">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560868">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560887">DXGKMDT_OPM_OMAC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560890">DXGKMDT_OPM_OUTPUT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560925">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>
 

 

