---
UID: NF:prcomoem.IPrintCoreHelper.SetFontSubstitution
title: IPrintCoreHelper::SetFontSubstitution method
author: windows-driver-content
description: The IPrintCoreHelper::SetFontSubstitution method specifies the device font to print in place of a given TrueType font.
old-location: print\iprintcorehelper_setfontsubstitution.htm
old-project: print
ms.assetid: 2d0278b0-0011-4946-a095-5fef77a8b194
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IPrintCoreHelper, print.iprintcorehelper_setfontsubstitution, print_unidrv-pscript_allplugins_4ac54a23-3b42-4bb7-a078-a53774a537b2.xml, IPrintCoreHelper::SetFontSubstitution, SetFontSubstitution method [Print Devices], IPrintCoreHelper interface, SetFontSubstitution method [Print Devices], IPrintCoreHelper interface [Print Devices], SetFontSubstitution method, prcomoem/IPrintCoreHelper::SetFontSubstitution, SetFontSubstitution
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintCoreHelper.SetFontSubstitution
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintCoreHelper::SetFontSubstitution method


## -description


The <b>IPrintCoreHelper::SetFontSubstitution</b> method specifies the device font to print in place of a given TrueType font. 


## -syntax


````
HRESULT SetFontSubstitution(
  [in] PCWSTR pszTrueTypeFontName,
  [in] PCWSTR pszDevFontName
);
````


## -parameters




### -param pszTrueTypeFontName [in]

A pointer to a null-terminated Unicode string that contains a valid TrueType font name. This parameter must not be <b>NULL</b>.


### -param pszDevFontName [in]

A pointer to a null-terminated Unicode string that contains the name of the device font. 


## -returns



<b>IPrintCoreHelper::SetFontSubstitution</b> should return one of the following values.

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



Setting a device font to use in place of a specified TrueType font can occur only during the device property sheets session and only if full UI replacement is enabled. The font that is represented by the <i>pszTrueTypeFontName</i> parameter must be a valid TrueType font and must be installed on the printer. The device font that is represented by the <i>pszDevFontName</i> parameter must be a valid font for this printer.

If a substitution mapping for the specified TrueType font already exists on this queue, the <b>SetFontSubstitution</b> method will silently replace the mapping. To remove a substitution mapping, call this method with the TrueType font name specified in <i>pszTrueTypeFontName</i> and with <b>NULL</b> specified in <i>pszDevFontName</i>.

To obtain a list of valid device fonts, create an information context for the current printer, and call <b>SetGraphicsMode</b>(hIC, GM_ADVANCED). Then, enumerate device fonts by means of a call to <b>EnumFontFamilies</b>. The callback parameter (see <b>EnumFontFamProc</b> in the Microsoft Windows SDK documentation) of <b>EnumFontFamilies</b> should filter for device fonts by incrementing a counter for each font for which the bitwise AND result (FontType &amp; TRUETYPE_FONTTYPE) is nonzero.

<div class="alert"><b>Note</b>  The <b>SetGraphicsMode</b>, <b>EnumFontFamilies</b>, and <b>EnumFontFamProc</b> functions are described in the Windows SDK documentation.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552957">IPrintCoreHelper::GetFontSubstitution</a>



<a href="https://msdn.microsoft.com/db13410f-e4cb-4077-bb4b-7963e97b435c">IPrintCoreHelper</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelper::SetFontSubstitution method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

