---
UID: NF:prcomoem.IPrintCoreHelper.SetFontSubstitution
title: IPrintCoreHelper::SetFontSubstitution (prcomoem.h)
description: The IPrintCoreHelper::SetFontSubstitution method specifies the device font to print in place of a given TrueType font.
tech.root: print
ms.date: 11/28/2022
keywords: ["IPrintCoreHelper::SetFontSubstitution"]
ms.keywords: IPrintCoreHelper interface [Print Devices],SetFontSubstitution method, IPrintCoreHelper.SetFontSubstitution, IPrintCoreHelper::SetFontSubstitution, SetFontSubstitution, SetFontSubstitution method [Print Devices], SetFontSubstitution method [Print Devices],IPrintCoreHelper interface, prcomoem/IPrintCoreHelper::SetFontSubstitution, print.iprintcorehelper_setfontsubstitution, print_unidrv-pscript_allplugins_4ac54a23-3b42-4bb7-a078-a53774a537b2.xml
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
 - IPrintCoreHelper::SetFontSubstitution
 - prcomoem/IPrintCoreHelper::SetFontSubstitution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCoreHelper::SetFontSubstitution
---

## -description

The **IPrintCoreHelper::SetFontSubstitution** method specifies the device font to print in place of a given TrueType font.

## -parameters

### -param pszTrueTypeFontName [in]

A pointer to a null-terminated Unicode string that contains a valid TrueType font name. This parameter must not be **NULL**.

### -param pszDevFontName [in]

A pointer to a null-terminated Unicode string that contains the name of the device font.

## -returns

**IPrintCoreHelper::SetFontSubstitution** should return one of the following values:

| Return code | Description |
|---|---|
| **S_OK** | The method read the option for the specified feature. |
| **E_FAIL** | The font that was requested does not exist or was not a TrueType font. |
| **E_INVALIDARG** | One or more of the arguments is invalid. |
| **E_OUTOFMEMORY** | The core driver was not able to service the request because there was insufficient memory. |
| **E_UNEXPECTED, or other return codes not listed here** | The core driver seems to be in an invalid state. The caller should return a failure code. |

## -remarks

Setting a device font to use in place of a specified TrueType font can occur only during the device property sheets session and only if full UI replacement is enabled. The font that is represented by the *pszTrueTypeFontName* parameter must be a valid TrueType font and must be installed on the printer. The device font that is represented by the *pszDevFontName* parameter must be a valid font for this printer.

If a substitution mapping for the specified TrueType font already exists on this queue, the **SetFontSubstitution** method will silently replace the mapping. To remove a substitution mapping, call this method with the TrueType font name specified in *pszTrueTypeFontName* and with **NULL** specified in *pszDevFontName*.

To obtain a list of valid device fonts, create an information context for the current printer, and call [**SetGraphicsMode**(hIC, GM_ADVANCED)](/windows/win32/api/wingdi/nf-wingdi-setgraphicsmode). Then, enumerate device fonts by means of a call to [**EnumFontFamilies**](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesa). The callback parameter ((see [**EnumFontFamProc**](/previous-versions/dd162621(v=vs.85))) of [**EnumFontFamilies**](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesa) should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType & TRUETYPE_FONTTYPE) is nonzero.

## -see-also

[IPrintCoreHelper](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper)

[IPrintCoreHelper::GetFontSubstitution](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-getfontsubstitution)
