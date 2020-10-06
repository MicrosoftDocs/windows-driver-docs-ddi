---
UID: NF:prcomoem.IPrintCoreHelperUni.GetFontSubstitution
title: IPrintCoreHelperUni::GetFontSubstitution (prcomoem.h)
description: The IPrintCoreHelperUni::GetFontSubstitution method indicates which device font, if any, is used as a substitution font for a specified TrueType font.
old-location: print\iprintcorehelperuni_getfontsubstitution.htm
tech.root: print
ms.assetid: f11b3b85-d01b-4133-9279-bff0001e04f9
ms.date: 04/20/2018
keywords: ["IPrintCoreHelperUni::GetFontSubstitution"]
ms.keywords: GetFontSubstitution, GetFontSubstitution method [Print Devices], GetFontSubstitution method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],GetFontSubstitution method, IPrintCoreHelperUni.GetFontSubstitution, IPrintCoreHelperUni::GetFontSubstitution, prcomoem/IPrintCoreHelperUni::GetFontSubstitution, print.iprintcorehelperuni_getfontsubstitution, print_unidrv-pscript_allplugins_9ce6a5aa-84f7-4193-8dcc-1e4a12b91b19.xml
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintCoreHelperUni::GetFontSubstitution
 - prcomoem/IPrintCoreHelperUni::GetFontSubstitution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperUni.GetFontSubstitution
---

# IPrintCoreHelperUni::GetFontSubstitution


## -description

The <code>IPrintCoreHelperUni::GetFontSubstitution</code> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

## -parameters

### -param pszTrueTypeFontName 

[in]
A pointer to a null-terminated Unicode string that contains the name of a TrueType font.

### -param ppszDevFontName 

[out]
A pointer to a variable that receives the address of a null-terminated Unicode string. This string contains the name of the device font that will be used in place of the TrueType font specified in the <i>pszFontName</i> parameter. If there is no device font that can serve as a substitute for the specified TrueType font, this parameter will be set to <b>NULL</b>.

## -returns

<code>IPrintCoreHelperUni::GetFontSubstitution</code> should return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method read the option for the specified feature.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The font that was requested does not exist or was not a TrueType font.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more of the arguments is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The core driver was not able to service the request because there was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED, or other return codes not listed here</b></dt>
</dl>
</td>
<td width="60%">
The core driver seems to be in an invalid state. The caller should return a failure code.

</td>
</tr>
</table>

## -remarks

If an application attempts to print text that uses the TrueType font specified in the <i>pszTrueTypeFontName</i> parameter, that text will instead be printed in the device font specified in the <i>ppszDevFontName</i> parameter. The device font name must be that of a valid, installed font.

A font is identified by its font face name, which appears in the <b>lfFaceName</b> member of the LOGFONT structure.

To obtain a list of available fonts, create an information context for the current printer, and call <b>SetGraphicsMode</b>(hIC, GM_ADVANCED). Then enumerate device fonts by calling <b>EnumFontFamilies</b>. The callback parameter (see <b>EnumFontFamProc</b> in the Microsoft Windows SDK documentation) of <b>EnumFontFamilies</b> should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType & TRUETYPE_FONTTYPE) is nonzero.

<div class="alert"><b>Note</b>  See the Windows SDK documentation for information about the structures and functions described previously.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni">IPrintCoreHelperUni</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-setfontsubstitution">IPrintCoreHelperUni::SetFontSubstitution</a>