---
UID: NS:dxva._DXVA_TCoefSingle
title: "_DXVA_TCoefSingle"
author: windows-driver-content
description: The DXVA_TCoefSingle structure is sent by the host decoder to the accelerator to specify IDCT coefficient values.
old-location: display\dxva_tcoefsingle.htm
old-project: display
ms.assetid: 665a9819-d319-414d-9a31-ee565b293197
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *LPDXVA_TCoefSingle, ,, A, C, D, DXVA_TCoefSingle, DXVA_TCoefSingle structure [Display Devices], L, LPDXVA_TCoefSingle, LPDXVA_TCoefSingle structure pointer [Display Devices], P, S, T, V, X, _, _DXVA_TCoefSingle, display.dxva_tcoefsingle, dxva/DXVA_TCoefSingle, dxva/LPDXVA_TCoefSingle, dxvaref_2b92ced3-3856-466f-b95a-84dd78426a0e.xml, e, f, g, i, l, n, o"
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
-	DXVA_TCoefSingle
product: Windows
targetos: Windows
req.typenames: DXVA_TCoefSingle, *LPDXVA_TCoefSingle
---

# _DXVA_TCoefSingle structure


## -description


The DXVA_TCoefSingle structure is sent by the host decoder to the accelerator to specify <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">IDCT</a> coefficient values.


## -syntax


````
typedef struct _DXVA_TCoefSingle {
  WORD  wIndexWithEOB;
  SHORT TCoefValue;
} DXVA_TCoefSingle, *LPDXVA_TCoefSingle;
````


## -struct-fields




### -field wIndexWithEOB

This member contains two fields: <i>TCoefIDX </i>and <i>TCoefEOB</i>.





#### TCoefIDX

Specifies the scan index of the coefficient in the block, as determined from the <b>bConfigHostInverseScan</b> member of the <a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a> structure. This field is in the 15 most significant bits of the <b>wIndexWithEOB </b>member.

There are two ways that <i>TCoefIDX</i> can be used:

<ol>
<li>
Run-length ordering: When <b>bConfigHostInverseScan</b> is zero, the <i>MBscanMethod</i> element of the macroblock control command indicates a zigzag, alternate-vertical, or alternate-horizontal inverse scan. These macroblock control commands are defined in the following structures: <a href="..\dxva\ns-dxva-_dxva_mbctrl_i_offhostidct_1.md">DXVA_MBctrl_I_OffHostIDCT_1</a> or <a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a>. In this case, <i>TCoefIDX</i> contains the number of zero-valued coefficients that precede the current coefficient in the specified scan order, subsequent to the last transmitted coefficient for the block (or relative to the start of the block if none precede it). Any remaining coefficients after the last sent coefficient in the inverse-scan order are implied to have the value zero.

</li>
<li>
Arbitrary ordering: When <b>bConfigHostInverseScan</b> is 1, the <i>MBscanMethod</i> element of the macroblock control command indicates arbitrary ordering. These macroblock control commands are defined in the following structures: <a href="..\dxva\ns-dxva-_dxva_mbctrl_i_offhostidct_1.md">DXVA_MBctrl_I_OffHostIDCT_1</a> and <a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a>. In this case, <i>TCoefIDX</i> simply contains the raster index of the coefficient within the block (TCoefIDX = u + 8 * v, where u and v are the transform-domain horizontal and vertical frequency coordinates), and any coefficients that are not sent are implied to have the value 0.

</li>
</ol>
<i>TCoefIDX</i> must always be less than 64.



#### TCoefEOB

Indicates whether the current coefficient is the last one associated with the current block of transform coefficients. A value of 1 indicates that the current coefficient is the last one for the block and a value of zero indicates that it is not. This field is in the least significant bit of the <b>wIndexWithEOB</b> member. 


### -field TCoefValue

Indicates the value of the coefficient in the block. <b>TCoefValue</b> must be clipped to the appropriate range as specified in <a href="https://msdn.microsoft.com/7736a226-1122-4380-b09f-a8560c0cd609">Low-Level IDCT Processing Elements</a> by the host prior to passing the coefficient value to the accelerator for <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">IDCT</a> operation. MPEG-2 mismatch control, if necessary, is also the responsibility of the host, not the accelerator. (This might require the creation of extra "phantom" nonzero coefficients.)


## -remarks



The DXVA_TCoefSingle structure is used whenever the <i>HostResidDiff</i> flag (bit 10 in the <b>wMBtype</b> member of the <a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a> or <a href="..\dxva\ns-dxva-_dxva_mbctrl_i_offhostidct_1.md">DXVA_MBctrl_I_OffHostIDCT_1</a> structure) is 1 and the <b>bConfig4GroupedCoefs</b> member of the <a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a> structure is zero.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_mbctrl_p_offhostidct_1.md">DXVA_MBctrl_P_OffHostIDCT_1</a>



<a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a>



<a href="..\dxva\ns-dxva-_dxva_mbctrl_i_offhostidct_1.md">DXVA_MBctrl_I_OffHostIDCT_1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_TCoefSingle structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

