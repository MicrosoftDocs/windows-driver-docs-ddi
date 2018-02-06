---
UID: NE:icm.COLORPROFILETYPE
title: COLORPROFILETYPE
author: windows-driver-content
description: The COLORPROFILETYPE enumeration is used to specify the type of color profile.
old-location: print\colorprofiletype.htm
old-project: print
ms.assetid: 756ba822-ace2-4893-a989-9d355434e57c
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: colorfnc_409d0d83-91ea-408a-8970-4de6e9cf94eb.xml, icm/CPT_CAMP, print.colorprofiletype, COLORPROFILETYPE enumeration [Print Devices], CPT_DMP, *PCOLORPROFILETYPE, icm/CPT_DMP, COLORPROFILETYPE, CPT_ICC, CPT_CAMP, CPT_GMMP, icm/CPT_GMMP, icm/CPT_ICC, icm/COLORPROFILETYPE
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	icm.h
apiname:
-	COLORPROFILETYPE
product: Windows
targetos: Windows
req.typenames: COLORPROFILETYPE
---

# COLORPROFILETYPE enumeration


## -description


The COLORPROFILETYPE enumeration is used to specify the type of color profile.


## -syntax


````
typedef enum  { 
  CPT_ICC   = 0,
  CPT_DMP   = 1,
  CPT_CAMP  = 2,
  CPT_GMMP  = 3
} COLORPROFILETYPE;
````


## -enum-fields




### -field CPT_ICC

Specifies an ICC profile. If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> are valid.


### -field CPT_DMP

Specifies a WCS device model profile (DMP). If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> are valid.


### -field CPT_CAMP

Specifies a WCS color appearance model profile (CAMP). If this value is specified, only the CPST_NONE value of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> is valid.


### -field CPT_GMMP

Specifies a WCS gamut map model profile (GMMP). If this value is specified, only the CPST_PERCEPTUAL, CPST_SATURATION, CPST_RELATIVE_COLORIMETRIC, and CPST_ABSOLUTE_COLORIMETRIC values of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> are valid. Any one of these values may optionally be combined (in a bitwise OR operation) with CPST_DEFAULT.


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

<a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20COLORPROFILETYPE enumeration%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

