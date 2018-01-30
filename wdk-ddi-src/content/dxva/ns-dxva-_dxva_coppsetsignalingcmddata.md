---
UID: NS:dxva._DXVA_COPPSetSignalingCmdData
title: "_DXVA_COPPSetSignalingCmdData"
author: windows-driver-content
description: The DXVA_COPPSetSignalingCmdData structure describes how to protect the signal that goes through the physical connector associated with the DirectX VA COPP device.
old-location: display\dxva_coppsetsignalingcmddata.htm
old-project: display
ms.assetid: 88318bb4-bfca-4557-93cb-703840fa692e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_COPPSetSignalingCmdData, dxvaref_2fd69b63-8cfc-427f-9616-4de12bd1a848.xml, DXVA_COPPSetSignalingCmdData structure [Display Devices], _DXVA_COPPSetSignalingCmdData, display.dxva_coppsetsignalingcmddata, dxva/DXVA_COPPSetSignalingCmdData
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxva.h
apiname:
-	DXVA_COPPSetSignalingCmdData
product: Windows
targetos: Windows
req.typenames: DXVA_COPPSetSignalingCmdData
---

# _DXVA_COPPSetSignalingCmdData structure


## -description


The DXVA_COPPSetSignalingCmdData structure describes how to protect the signal that goes through the physical connector associated with the DirectX VA COPP device.


## -syntax


````
typedef struct _DXVA_COPPSetSignalingCmdData {
  ULONG ActiveTVProtectionStandard;
  ULONG AspectRatioChangeMask1;
  ULONG AspectRatioData1;
  ULONG AspectRatioChangeMask2;
  ULONG AspectRatioData2;
  ULONG AspectRatioChangeMask3;
  ULONG AspectRatioData3;
  ULONG ExtendedInfoChangeMask[4];
  ULONG ExtendedInfoData[4];
  ULONG Reserved;
} DXVA_COPPSetSignalingCmdData;
````


## -struct-fields




### -field ActiveTVProtectionStandard

Specifies a valid ORed combination of the following values from the <b>COPP_TVProtectionStandard</b> enumeration type that indicates the type of television signals on which to set protection:
<ul>
<li>
COPP_ProtectionStandard_Unknown (0x80000000)

</li>
<li>
COPP_ProtectionStandard_None (0x00000000)

</li>
<li>
COPP_ProtectionStandard_IEC61880_525i (0x00000001)

</li>
<li>
COPP_ProtectionStandard_IEC61880_2_525i (0x00000002)

</li>
<li>
COPP_ProtectionStandard_IEC62375_625p (0x00000004)

</li>
<li>
COPP_ProtectionStandard_EIA608B_525 (0x00000008)

</li>
<li>
COPP_ProtectionStandard_EN300294_625i (0x00000010)

</li>
<li>
COPP_ProtectionStandard_CEA805A_TypeA_525p (0x00000020)

</li>
<li>
COPP_ProtectionStandard_CEA805A_TypeA_750p (0x00000040)

</li>
<li>
COPP_ProtectionStandard_CEA805A_TypeA_1125i (0x00000080)

</li>
<li>
COPP_ProtectionStandard_CEA805A_TypeB_525p (0x00000100)

</li>
<li>
COPP_ProtectionStandard_CEA805A_TypeB_750p (0x00000200)

</li>
<li>
COPP_ProtectionStandard_CEA805A_TypeB_1125i (0x00000400)

</li>
<li>
COPP_ProtectionStandard_ARIBTRB15_525i (0x00000800)

</li>
<li>
COPP_ProtectionStandard_ARIBTRB15_525p (0x00001000)

</li>
<li>
COPP_ProtectionStandard_ARIBTRB15_750p (0x00002000)

</li>
<li>
COPP_ProtectionStandard_ARIBTRB15_1125i (0x00004000)

</li>
</ul>

### -field AspectRatioChangeMask1

Specifies the COPP_ImageAspectRatio_EN300294_Mask (0x00000007) constant that indicates that only the first 3 bits in the following <b>AspectRatioData1</b> member are valid.


### -field AspectRatioData1

Specifies one of the following values from the <b>COPP_ImageAspectRatio_EN300294</b> enumeration type to indicate an ETSI EN 300 294 value.
<ul>
<li>
COPP_AspectRatio_EN300294_FullFormat4by3 (0)

</li>
<li>
COPP_AspectRatio_EN300294_Box14by9Center (1)

</li>
<li>
COPP_AspectRatio_EN300294_Box14by9Top (2)

</li>
<li>
COPP_AspectRatio_EN300294_Box16by9Center (3)

</li>
<li>
COPP_AspectRatio_EN300294_Box16by9Top (4)

</li>
<li>
COPP_AspectRatio_EN300294_BoxGT16by9Center (5)

</li>
<li>
COPP_AspectRatio_EN300294_FullFormat4by3ProtectedCenter (6)

</li>
<li>
COPP_AspectRatio_EN300294_FullFormat16by9Anamorphic (7)

</li>
</ul>

### -field AspectRatioChangeMask2

Specifies a value that indicates the valid bitfields in the following <b>AspectRatioData2</b> member.


### -field AspectRatioData2

Specifies 32-bit data for additional aspect ratio-related data to be set for specific protection standards. This data can be used to express End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.


### -field AspectRatioChangeMask3

Specifies a value that indicates the valid bitfields in the following <b>AspectRatioData3</b> member.


### -field AspectRatioData3

Specifies 32-bit data for additional aspect ratio-related data to be set for specific protection standards. This data can be used to express End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.


### -field ExtendedInfoChangeMask

Specifies an array of values that indicate the valid bitfields in the respective elements of the following <b>ExtendedInfoData</b> array member.


### -field ExtendedInfoData

Specifies an array of additional 32-bit data values to be set. Not currently used.


### -field Reserved

Reserved. Should be set to zero.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_coppcommand.md">DXVA_COPPCommand</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539642">COPPCommand</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPSetSignalingCmdData structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

