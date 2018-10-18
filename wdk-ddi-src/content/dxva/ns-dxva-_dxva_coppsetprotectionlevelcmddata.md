---
UID: NS:dxva._DXVA_COPPSetProtectionLevelCmdData
title: "_DXVA_COPPSetProtectionLevelCmdData"
author: windows-driver-content
description: The DXVA_COPPSetProtectionLevelCmdData structure describes the protection types and levels to set on the physical connector associated with a COPP DirectX VA device.
old-location: display\dxva_coppsetprotectionlevelcmddata.htm
tech.root: display
ms.assetid: d68d6e50-1373-43bc-a22b-dd9db47614c8
ms.date: 5/10/2018
ms.keywords: DXVA_COPPSetProtectionLevelCmdData, DXVA_COPPSetProtectionLevelCmdData structure [Display Devices], _DXVA_COPPSetProtectionLevelCmdData, display.dxva_coppsetprotectionlevelcmddata, dxva/DXVA_COPPSetProtectionLevelCmdData, dxvaref_ac7e802b-dd23-49da-ab02-21d80eaabe86.xml
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
-	DXVA_COPPSetProtectionLevelCmdData
product:
- Windows
targetos: Windows
req.typenames: DXVA_COPPSetProtectionLevelCmdData
---

# _DXVA_COPPSetProtectionLevelCmdData structure


## -description


The DXVA_COPPSetProtectionLevelCmdData structure describes the protection types and levels to set on the physical connector associated with a COPP DirectX VA device.


## -struct-fields




### -field ProtType

Specifies one of the following protection types to set on the physical connector associated with a COPP device:

<ul>
<li>
COPP_ProtectionType_None (0x00)

</li>
<li>
COPP_ProtectionType_HDCP (0x01)

</li>
<li>
COPP_ProtectionType_ACP (0x02)

</li>
<li>
COPP_ProtectionType_CGMSA (0x04)

</li>
</ul>

### -field ProtLevel

Specifies the protection level to set for the protection type in <b>ProtType</b> or COPP_NoProtectionLevelAvailable (-1) if no protection level is available.

<ul>
<li>For COPP_ProtectionType_ACP, specifies one of the following values from the <b>COPP_ACP_Protection_Level</b> enumerated type:<ul>
<li>COPP_ACP_Level0 or COPP_ACP_LevelMin (0)</li>
<li>COPP_ACP_Level1 (1)</li>
<li>COPP_ACP_Level2 (2)</li>
<li>COPP_ACP_Level3 or COPP_ACP_LevelMax (3)</li>
</ul>
</li>
<li>For COPP_ProtectionType_CGMSA, specifies one of the following values from the <b>COPP_CGMSA_Protection_Level</b> enumerated type:<ul>
<li>COPP_CGMSA_Disabled or COPP_CGMSA_LevelMin (0)</li>
<li>COPP_CGMSA_CopyFreely (1)</li>
<li>COPP_CGMSA_CopyNoMore (2)</li>
<li>COPP_CGMSA_CopyOneGeneration (3)</li>
<li>COPP_CGMSA_CopyNever (4)</li>
<li>COPP_CGMSA_RedistributionControlRequired (0x08)</li>
<li>(COPP_CGMSA_RedistributionControlRequired + COPP_CGMSA_CopyNever) or COPP_CGMSA_LevelMax</li>
</ul>
</li>
<li>For COPP_ProtectionType_HDCP, specifies one of the following values from the <b>COPP_HDCP_Protection_Level</b> enumerated type:<ul>
<li>COPP_HDCP_Level0 or COPP_HDCP_LevelMin (0)</li>
<li>COPP_HDCP_Level1 or COPP_HDCP_LevelMax (1)</li>
</ul>
</li>
</ul>

### -field ExtendedInfoChangeMask

Specifies a value that indicates the valid bitfields in the following <b>ExtendedInfoData</b> member.


### -field ExtendedInfoData

Specifies additional 32-bit data for the protection type in <b>ProtType</b>. Not currently used.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539642">COPPCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563141">DXVA_COPPCommand</a>
 

 

