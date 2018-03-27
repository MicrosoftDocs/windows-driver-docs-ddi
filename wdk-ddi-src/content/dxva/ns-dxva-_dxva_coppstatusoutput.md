---
UID: NS:dxva._DXVA_COPPStatusOutput
title: "_DXVA_COPPStatusOutput"
author: windows-driver-content
description: The DXVA_COPPStatusOutput structure describes the status returned from a query on a protected video session that is associated with a DirectX VA COPP device.
old-location: display\dxva_coppstatusoutput.htm
old-project: display
ms.assetid: 71d16b59-3e5c-4a2a-9217-5e0f7a2d4478
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPDXVA_COPPStatusOutput, DXVA_COPPStatusOutput, DXVA_COPPStatusOutput structure [Display Devices], LPDXVA_COPPStatusOutput, LPDXVA_COPPStatusOutput structure pointer [Display Devices], _DXVA_COPPStatusOutput, display.dxva_coppstatusoutput, dxva/DXVA_COPPStatusOutput, dxva/LPDXVA_COPPStatusOutput, dxvaref_4b7212ce-7beb-45c6-b5dd-92922993595f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
api_name:
-	DXVA_COPPStatusOutput
product: Windows
targetos: Windows
req.typenames: DXVA_COPPStatusOutput, *LPDXVA_COPPStatusOutput
---

# _DXVA_COPPStatusOutput structure


## -description


The DXVA_COPPStatusOutput structure describes the status returned from a query on a protected video session that is associated with a DirectX VA COPP device.


## -struct-fields




### -field macKDI

Specifies a message authentication code (MAC) GUID for the status at <b>COPPStatus</b>. The application that requested the status can use the MAC to verify that the transmission of the status was secure (that is, it was not tampered with in transit from the driver). 


### -field cbSizeData

Specifies the size, in bytes, of the status data at <b>COPPStatus</b>.


### -field COPPStatus

Specifies an array that contains the status data. The display driver should return status data in one of the following ways, depending on the input value that was specified in the <b>guidStatusRequestID</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563899">DXVA_COPPStatusInput</a> structure: 

<table>
<tr>
<th>Input value</th>
<th>Output status data</th>
</tr>
<tr>
<td>
DXVA_COPPQueryDisplayData

</td>
<td>
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563157">DXVA_COPPStatusDisplayData</a> structure

</td>
</tr>
<tr>
<td>

<dl>
<dt>DXVA_COPPQueryProtectionType, </dt>
<dt>DXVA_COPPQueryConnectorType, </dt>
<dt>DXVA_COPPQueryLocalProtectionLevel, </dt>
<dt>DXVA_COPPQueryGlobalProtectionLevel or </dt>
<dt>DXVA_COPPQueryBusData</dt>
</dl>


</td>
<td>
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563154">DXVA_COPPStatusData</a> structure

</td>
</tr>
<tr>
<td>
DXVA_COPPQueryHDCPKeyData

</td>
<td>
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563896">DXVA_COPPStatusHDCPKeyData</a> structure

</td>
</tr>
<tr>
<td>
DXVA_COPPQuerySignaling

</td>
<td>
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563905">DXVA_COPPStatusSignalingCmdData</a> structure

</td>
</tr>
</table>
 


## -remarks



Status requests are passed in the <i>pInput</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a> function. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff563899">DXVA_COPPStatusInput</a> structure describes a request for status. Status information is returned through the <i>pOutput</i> parameter of <i>COPPQueryStatus</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563143">DXVA_COPPSetProtectionLevelCmdData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563154">DXVA_COPPStatusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563157">DXVA_COPPStatusDisplayData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563896">DXVA_COPPStatusHDCPKeyData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563899">DXVA_COPPStatusInput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563905">DXVA_COPPStatusSignalingCmdData</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPStatusOutput structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

