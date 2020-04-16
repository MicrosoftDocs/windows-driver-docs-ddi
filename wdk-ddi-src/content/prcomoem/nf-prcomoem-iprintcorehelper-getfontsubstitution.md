---
UID: NF:prcomoem.IPrintCoreHelper.GetFontSubstitution
title: IPrintCoreHelper::GetFontSubstitution (prcomoem.h)
description: The IPrintCoreHelper::GetFontSubstitution method indicates which device font, if any, is used as a substitution font for a specified TrueType font.
old-location: print\iprintcorehelper_getfontsubstitution.htm
tech.root: print
ms.assetid: 09fc48eb-b124-45b1-a796-71d9a6961e07
ms.date: 04/20/2018
keywords: ["IPrintCoreHelper::GetFontSubstitution"]
ms.keywords: GetFontSubstitution, GetFontSubstitution method [Print Devices], GetFontSubstitution method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],GetFontSubstitution method, IPrintCoreHelper.GetFontSubstitution, IPrintCoreHelper::GetFontSubstitution, prcomoem/IPrintCoreHelper::GetFontSubstitution, print.iprintcorehelper_getfontsubstitution, print_unidrv-pscript_allplugins_04228fad-ab7f-432f-b4b9-dafb18144503.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelper.GetFontSubstitution"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintCoreHelper.GetFontSubstitution
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelper::GetFontSubstitution


## -description


The <b>IPrintCoreHelper::GetFontSubstitution</b> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.


## -parameters




### -param pszTrueTypeFontName [in]

A pointer to a null-terminated Unicode string that contains the name of a TrueType font. 


### -param ppszDevFontName [out]

A pointer to a variable that receives the address of a null-terminated Unicode string. This string contains the name of the device font that will be used in place of the TrueType font specified in the <i>pszFontName</i> parameter. If there is no device font that can serve as a substitute for the specified TrueType font, this parameter is set to <b>NULL</b>.


## -returns



<b>IPrintCoreHelper::GetFontSubstitution</b> should return one of the following values.

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
<dt><b>E_UNEXPECTED, or other return codes not listed elsewhere in this table</b></dt>
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

To obtain a list of available fonts, create an information context for the current printer, and call SetGraphicsMode(hIC, GM_ADVANCED). Then enumerate device fonts by means of a call to EnumFontFamilies. The callback parameter (see EnumFontFamProc in the Microsoft Windows SDK documentation) of EnumFontFamilies should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType & TRUETYPE_FONTTYPE) is nonzero.

<div class="alert"><b>Note</b>  For more information about the structures and functions described previously, see the Windows SDK documentation.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper">IPrintCoreHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-setfontsubstitution">IPrintCoreHelper::SetFontSubstitution</a>
 

 

