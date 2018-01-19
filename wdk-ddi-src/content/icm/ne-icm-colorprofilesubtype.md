---
UID: NE:icm.COLORPROFILESUBTYPE
title: COLORPROFILESUBTYPE
author: windows-driver-content
description: The COLORPROFILESUBTYPE enumeration is used to specify the subtype of color profile.
old-location: print\colorprofilesubtype.htm
old-project: print
ms.assetid: 7ec0dd2d-7be5-4c85-8096-64a45aee01a5
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: COLORPROFILESUBTYPE, COLORPROFILESUBTYPE, *PCOLORPROFILESUBTYPE
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
req.alt-api: COLORPROFILESUBTYPE
req.alt-loc: icm.h
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
req.typenames: COLORPROFILESUBTYPE
---

# COLORPROFILESUBTYPE enumeration



## -description
The COLORPROFILESUBTYPE enumeration is used to specify the subtype of color profile.



## -syntax

````
typedef enum  { 
  CPST_PERCEPTUAL             = INTENT_PERCEPTUAL,
  CPST_RELATIVE_COLORIMETRIC  = INTENT_RELATIVE_COLORIMETRIC,
  CPST_SATURATION             = INTENT_SATURATION,
  CPST_ABSOLUTE_COLORIMETRIC  = INTENT_ABSOLUTE_COLORIMETRIC,
  CPST_NONE                   = 1,
  CPST_RGB_WORKING_SPACE      = 2,
  CPST_CUSTOM_WORKING_SPACE   = 3
} COLORPROFILESUBTYPE;
````


## -enum-fields

### -field CPST_PERCEPTUAL

Specifies a perceptual rendering intent for WCS gamut map model profiles (GMMPs).


### -field CPST_RELATIVE_COLORIMETRIC

Specifies a relative colorimetric rendering intent for WCS GMMPs.


### -field CPST_SATURATION

Specifies a saturation rendering intent for WCS GMMPs.


### -field CPST_ABSOLUTE_COLORIMETRIC

Specifies an absolute colorimetric rendering intent for WCS GMMPs.


### -field CPST_NONE

Specifies that the color profile subtype is not applicable to the selected color profile type.


### -field CPST_RGB_WORKING_SPACE

Specifies the RGB color working space for ICC profiles or WCS device model profiles (DMPs).


### -field CPST_CUSTOM_WORKING_SPACE

Specifies a custom color working space.


## -remarks
For a description of rendering intents, see <a href="http://go.microsoft.com/fwlink/p/?linkid=52269">Rendering Intents</a> in the Windows SDK documentation.

The PCOLORPROFILESUBTYPE and LPCOLORPROFILESUBTYPE data types are defined as pointers to this enumeration:


## -see-also
<dl>
<dt>
<a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a>
</dt>
<dt>
<a href="..\icm\nf-icm-wcssetdefaultcolorprofile.md">WcsSetDefaultColorProfile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20COLORPROFILESUBTYPE enumeration%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

