---
UID: NF:prcomoem.IPrintCoreHelperPS.GetFontSubstitution
title: IPrintCoreHelperPS::GetFontSubstitution method
author: windows-driver-content
description: The IPrintCoreHelperPS::GetFontSubstitution method indicates which device font, if any, is used as a substitution font for a specified TrueType font.
old-location: print\iprintcorehelperps_getfontsubstitution.htm
old-project: print
ms.assetid: d5f71935-8371-413d-a602-a9a4a9e976c3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS::GetFontSubstitution, GetFontSubstitution
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintCoreHelperPS.GetFontSubstitution
req.alt-loc: Prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::GetFontSubstitution method



## -description
The <b>IPrintCoreHelperPS::GetFontSubstitution</b> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.



## -syntax

````
STDMETHOD GetFontSubstitution(
  [in]  PCWSTR pszTrueTypeFontName,
  [out] PCWSTR *ppszDevFontName
);
````


## -parameters

### -param pszTrueTypeFontName [in]

A pointer to a null-terminated Unicode string that contains the name of a TrueType font. 


### -param ppszDevFontName [out]

A pointer to a variable that receives the address of a null-terminated Unicode string. This string contains the name of the device font that will be used in place of the TrueType font specified in the <i>pszFontName</i> parameter. If there is no device font that can serve as a substitute for the specified TrueType font, this parameter will be set to <b>NULL</b>.


## -returns
<b>IPrintCoreHelperPS::GetFontSubstitution</b> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method read the option for the specified feature.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The font that was requested does not exist or was not a TrueType font.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>One or more of the arguments is invalid.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The core driver was not able to service the request because there was insufficient memory.
<dl>
<dt><b>E_UNEXPECTED, or other return codes not listed here</b></dt>
</dl>The core driver seems to be in an invalid state. The caller should return a failure code.

 


## -remarks
If an application attempts to print text that uses the TrueType font specified in the <i>pszTrueTypeFontName</i> parameter, that text will instead be printed in the device font specified in the <i>ppszDevFontName</i> parameter. The device font name must be that of a valid, installed font.

A font is identified by its font face name, which appears in the <b>lfFaceName</b> member of the LOGFONT structure.

To obtain a list of available fonts, create an information context for the current printer, and call <b>SetGraphicsMode</b>(hIC, GM_ADVANCED). Then enumerate device fonts by calling <b>EnumFontFamilies</b>. The callback parameter (see <b>EnumFontFamProc</b> in the Microsoft Windows SDK documentation) of <b>EnumFontFamilies</b> should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType &amp; TRUETYPE_FONTTYPE) is nonzero.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552908">IPrintCoreHelperPS::SetFontSubstitution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::GetFontSubstitution method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

