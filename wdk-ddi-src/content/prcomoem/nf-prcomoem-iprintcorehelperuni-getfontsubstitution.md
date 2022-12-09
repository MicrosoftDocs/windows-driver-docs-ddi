---
UID: NF:prcomoem.IPrintCoreHelperUni.GetFontSubstitution
title: IPrintCoreHelperUni::GetFontSubstitution (prcomoem.h)
description: The IPrintCoreHelperUni::GetFontSubstitution method indicates which device font, if any, is used as a substitution font for a specified TrueType font.
tech.root: print
ms.date: 11/30/2022
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
 - IPrintCoreHelperUni::GetFontSubstitution
---

## -description

**IPrintCoreHelperUni::GetFontSubstitution** method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

## -parameters

### -param pszTrueTypeFontName [in]

A pointer to a null-terminated Unicode string that contains the name of a TrueType font.

### -param ppszDevFontName [out]

A pointer to a variable that receives the address of a null-terminated Unicode string. This string contains the name of the device font that will be used in place of the TrueType font specified in the *pszFontName* parameter. If there is no device font that can serve as a substitute for the specified TrueType font, this parameter will be set to **NULL**.

## -returns

**IPrintCoreHelperUni::GetFontSubstitution** should return one of the following values:

| Return code | Description |
|---|---|
| **S_OK** | The method read the option for the specified feature. |
| **E_FAIL** | The font that was requested does not exist or was not a TrueType font. |
| **E_INVALIDARG** | One or more of the arguments is invalid. |
| **E_OUTOFMEMORY** | The core driver was not able to service the request because there was insufficient memory. |
| **E_UNEXPECTED, or other return codes not listed here** | The core driver seems to be in an invalid state. The caller should return a failure code. |

## -remarks

If an application attempts to print text that uses the TrueType font specified in the *pszTrueTypeFontName* parameter, that text will instead be printed in the device font specified in the *ppszDevFontName* parameter. The device font name must be that of a valid, installed font.

A font is identified by its font face name, which appears in the **lfFaceName** member of the [**LOGFONT**](/windows/win32/api/wingdi/ns-wingdi-logfonta) structure.

To obtain a list of available fonts, create an information context for the current printer, and call [**SetGraphicsMode**(hIC, GM_ADVANCED)](/windows/win32/api/wingdi/nf-wingdi-setgraphicsmode). Then enumerate device fonts by means of a call to [**EnumFontFamilies**](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesa). The callback parameter (see [**EnumFontFamProc**](/previous-versions/dd162621(v=vs.85))) of [**EnumFontFamilies**](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesa) should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType & TRUETYPE_FONTTYPE) is nonzero.

## -see-also

[IPrintCoreHelperUni](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni)

[IPrintCoreHelperUni::SetFontSubstitution](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-setfontsubstitution)
