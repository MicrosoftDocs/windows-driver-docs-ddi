---
UID: NE:icm.COLORPROFILETYPE
title: COLORPROFILETYPE
author: windows-driver-content
description: The COLORPROFILETYPE enumeration is used to specify the type of color profile.
old-location: print\colorprofiletype.htm
tech.root: print
ms.assetid: 756ba822-ace2-4893-a989-9d355434e57c
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: "*PCOLORPROFILETYPE, COLORPROFILETYPE, COLORPROFILETYPE enumeration [Print Devices], CPT_CAMP, CPT_DMP, CPT_GMMP, CPT_ICC, colorfnc_409d0d83-91ea-408a-8970-4de6e9cf94eb.xml, icm/COLORPROFILETYPE, icm/CPT_CAMP, icm/CPT_DMP, icm/CPT_GMMP, icm/CPT_ICC, print.colorprofiletype"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: icm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Included in Windows Vista and later.
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
-	icm.h
api_name:
-	COLORPROFILETYPE
product:
- Windows
targetos: Windows
req.typenames: COLORPROFILETYPE
---

# COLORPROFILETYPE enumeration


## -description


The COLORPROFILETYPE enumeration is used to specify the type of color profile.


## -enum-fields




### -field CPT_ICC

Specifies an ICC profile. If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> are valid.


### -field CPT_DMP

Specifies a WCS device model profile (DMP). If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> are valid.


### -field CPT_CAMP

Specifies a WCS color appearance model profile (CAMP). If this value is specified, only the CPST_NONE value of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> is valid.


### -field CPT_GMMP

Specifies a WCS gamut map model profile (GMMP). If this value is specified, only the CPST_PERCEPTUAL, CPST_SATURATION, CPST_RELATIVE_COLORIMETRIC, and CPST_ABSOLUTE_COLORIMETRIC values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> are valid. Any one of these values may optionally be combined (in a bitwise OR operation) with CPST_DEFAULT.


## -remarks



The PCOLORPROFILETYPE and LPCOLORPROFILETYPE data types are defined as pointers to this enumeration:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef COLORPROFILETYPE *PCOLORPROFILETYPE, *LPCOLORPROFILETYPE;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a>
 

 

