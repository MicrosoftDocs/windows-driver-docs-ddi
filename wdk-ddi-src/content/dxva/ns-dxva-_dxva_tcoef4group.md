---
UID: NS:dxva._DXVA_TCoef4Group
title: "_DXVA_TCoef4Group"
author: windows-driver-content
description: The DXVA_TCoef4Group structure is sent by the host decoder to the accelerator to specify the IDCT coefficient values.
old-location: display\dxva_tcoef4group.htm
old-project: display
ms.assetid: f7ffe847-58ae-42a9-86fd-50a757134b45
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXVA_TCoef4Group, dxva/DXVA_TCoef4Group, LPDXVA_TCoef4Group, *LPDXVA_TCoef4Group, dxvaref_40a4dc23-1488-41ad-ba76-296384236d78.xml, LPDXVA_TCoef4Group structure pointer [Display Devices], _DXVA_TCoef4Group, dxva/LPDXVA_TCoef4Group, DXVA_TCoef4Group structure [Display Devices], display.dxva_tcoef4group
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxva.h
apiname:
-	DXVA_TCoef4Group
product: Windows
targetos: Windows
req.typenames: DXVA_TCoef4Group, *LPDXVA_TCoef4Group
---

# _DXVA_TCoef4Group structure


## -description


The DXVA_TCoef4Group structure is sent by the host decoder to the accelerator to specify the IDCT coefficient values.


## -syntax


````
typedef struct _DXVA_TCoef4Group {
  BYTE  TCoefIDX[4];
  SHORT TCoefValue[4];
} DXVA_TCoef4Group, *LPDXVA_TCoef4Group;
````


## -struct-fields




### -field TCoefIDX

Specifies the scan index of the coefficient in the block. Expressed as the number of zero-valued coefficients that precede the current coefficient in the scan order specified by the <i>MBscanMethod</i> variable (bits 6 and 7 of the <b>wMBtype</b> member of the macroblock control command). These commands are defined in the following structures: <a href="..\dxva\ns-dxva-_dxva_mbctrl_i_offhostidct_1.md">DXVA_MBctrl_I_OffHostIDCT_1</a> or <a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a>. <b>TCoefIDX</b> contains the number of zero-valued coefficients that precede the current coefficient in the specified scan order, subsequent to the last transmitted coefficient for the block (or relative to the start of the block if none precede it). Any remaining coefficients after the last sent coefficient in the inverse-scan order are implied to have the value 0.

<b>TCoefIDX</b> must always be less than 64.


### -field TCoefValue

Specifies the value of the coefficient in the block. <b>TCoefValue</b> must be clipped to the appropriate range as specified in <a href="https://msdn.microsoft.com/7736a226-1122-4380-b09f-a8560c0cd609">Low-Level IDCT Processing Elements</a> by the host prior to passing the coefficient value to the accelerator for IDCT operation. MPEG-2 mismatch control, if necessary, is also the responsibility of the host, not the accelerator (this may require the creation of extra "phantom" nonzero coefficients).


## -remarks



The DXVA_TCoef4Group structure is used only when these two members of <a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a> structure are set to the following values: <b>bConfig4GroupedCoefs</b> is 1 and <b>bConfigHostInverseScan</b> is zero.

In the DXVA_TCoef4Group structure, groups of four transform coefficients are sent together with associated run-length values. The <i>i</i>th element of each array in DXVA_TCoef4Group contains element 3-<i>i</i> of the actual coefficient or run-length list (so the first coefficient or index goes into element 3, the next in element 2, and so forth). If only N<sub>C</sub> &lt; 4 nonzero coefficients remain that need to be sent for a block, then <b>TCoefIDX</b>[<i>i</i>] must be 63 (hexadecimal 0x3F), and <b>TCoefValue</b>[<i>i</i>] must be equal to <b>TCoefValue</b>[4-N<sub>C</sub>] for <i>i </i>= 0 to 3-N<sub>C</sub>.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_TCoef4Group structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

