---
UID: NF:wiamdef.WIAS_LHRESULT
title: WIAS_LHRESULT macro
author: windows-driver-content
description: The WIAS_LHRESULT macro is obsolete for Windows Vista and later. It is recommended that the WIAS_HRESULT macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file.
old-location: image\wias_lhresult.htm
old-project: image
ms.assetid: dcc02735-632f-4b86-ac4f-833c8dcba1c5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WIAS_LHRESULT macro [Imaging Devices], wiamdef/WIAS_LHRESULT, image.wias_lhresult, IWiaLog_f9693b87-6464-423a-9b50-f715f3b35f36.xml, WIAS_LHRESULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later. Use WIAS_HRESULT instead.
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
req.lib: wiamdef.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamdef.h
apiname:
-	WIAS_LHRESULT
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# WIAS_LHRESULT macro


## -description


The WIAS_LHRESULT macro is obsolete for Windows Vista and later. It is recommended that the <a href="..\wiamdef\nf-wiamdef-wias_hresult.md">WIAS_HRESULT</a> macro be used instead. The WIAS_LHRESULT macro translates an HRESULT value into a string and writes the string to the diagnostic log file.


## -syntax


````
VOID WIAS_LHRESULT(
   IWiaLog *pIWiaLog,
   HRESULT hr
);
````


## -parameters




### -param pILog

TBD


### -param hr

Specifies the HRESULT value to be translated into a string.


#### - pIWiaLog

Pointer to an <a href="..\wia_lh\nn-wia_lh-iwialog.md">IWiaLog Interface</a>.


## -remarks


The following is an example of how the macro can be used:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>hr = wiasFreePropContext(*pContext);
if (hr != S_OK)
   WIAS_LHRESULT(g_pIWiaLog, hr);</pre>
</td>
</tr>
</table></span></div>The WIAS_LHRESULT macro is not recommended for Windows Vista and later operating system versions. It is recommended that the <a href="..\wiamdef\nf-wiamdef-wias_hresult.md">WIAS_HRESULT</a> macro be used instead. 



## -see-also

<a href="..\wiamdef\nf-wiamdef-wias_lwarning.md">WIAS_LWARNING</a>

<a href="..\wiamdef\nf-wiamdef-wias_ltrace.md">WIAS_LTRACE</a>

<a href="..\wiamdef\nf-wiamdef-wias_lerror.md">WIAS_LERROR</a>

<a href="..\wiamdef\nf-wiamdef-wias_hresult.md">WIAS_HRESULT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_LHRESULT macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

