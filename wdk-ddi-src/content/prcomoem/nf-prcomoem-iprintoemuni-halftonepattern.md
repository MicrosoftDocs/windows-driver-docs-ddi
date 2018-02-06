---
UID: NF:prcomoem.IPrintOemUni.HalftonePattern
title: IPrintOemUni::HalftonePattern method
author: windows-driver-content
description: The IPrintOemUni::HalftonePattern method can be used with Unidrv-supported printers to create or modify a halftone pattern before it is used in a halftoning operation.
old-location: print\iprintoemuni_halftonepattern.htm
old-project: print
ms.assetid: 1b899492-f4a7-4c13-9e19-0f086b2b6b47
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: HalftonePattern, IPrintOemUni interface [Print Devices], HalftonePattern method, HalftonePattern method [Print Devices], HalftonePattern method [Print Devices], IPrintOemUni interface, IPrintOemUni, IPrintOemUni::HalftonePattern, print_unidrv-pscript_rendering_672da2b9-981c-4c4c-a303-88377fe01741.xml, prcomoem/IPrintOemUni::HalftonePattern, print.iprintoemuni_halftonepattern
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
-	IPrintOemUni.HalftonePattern
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintOemUni::HalftonePattern method


## -description


The <code>IPrintOemUni::HalftonePattern</code> method can be used with Unidrv-supported printers to create or modify a halftone pattern before it is used in a halftoning operation.


## -syntax


````
HRESULT HalftonePattern(
   PDEVOBJ pdevobj,
   PBYTE   pHTPattern,
   DWORD   dwHTPatternX,
   DWORD   dwHTPatternY,
   DWORD   dwHTNumPatterns,
   DWORD   dwCallbackID,
   PBYTE   pResource,
   DWORD   dwResourceSize
);
````


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pHTPattern

Caller-supplied pointer to a buffer that receives the method-supplied halftone pattern. Buffer size, in bytes, is:

(((<i>dwHTPatternX</i> * <i>dwHTPatternY</i>) + 3)/4) * 4 * <i>dwHTNumPatterns</i>.


### -param dwHTPatternX

Caller-supplied length, in pixels, of the halftone pattern, as specified by the first value in the <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> file's *<b>HTPatternSize</b> attribute.


### -param dwHTPatternY

Caller-supplied height, in pixels, of the halftone pattern, as specified by the second value in the GPD file's *<b>HTPatternSize</b> attribute.


### -param dwHTNumPatterns

Caller-supplied number of patterns, as specified by the GPD file's *<b>HTNumPatterns</b> attribute. The number of patterns can be either 1 or 3.


### -param dwCallbackID

Caller-supplied value identifying the halftone method, as specified by the GPD file's *<b>HTCallbackID</b> attribute.


### -param pResource

Caller-supplied pointer to a buffer containing a halftone pattern, as specified by the GPD file's *<b>rcHTPatternID</b> attribute. This can be <b>NULL</b>.


### -param dwResourceSize

Caller-supplied size of the halftone pattern contained in the buffer pointed to by <i>pResource</i>. This is zero if <i>pResource</i> is <b>NULL</b>.


## -returns


The method must return one of the following values.
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
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table> 



## -remarks


The <code>IPrintOemUni::HalftonePattern</code> method is used to create or modify a halftone pattern before Unidrv passes it to GDI. Its purpose is to allow proprietary halftone patterns to be either stored as encrypted resources or generated at run time.

If the <code>IPrintOemUni::HalftonePattern</code> method is implemented, and if the GPD file entry for the currently selected halftoning method includes an *<b>HTCallbackID</b> attribute, Unidrv calls the <code>IPrintOemUni::HalftonePattern</code> method before passing a halftone pattern to GDI.

If the GPD file entry for the currently selected halftoning method contains an *rcHTPatternID entry identifying an RC_HTPATTERN resource, Unidrv obtains the pattern and passes a pointer to it as the <i>pResource</i> parameter value. This allows you to store the pattern as an encrypted resource, and to use the <code>IPrintOemUni::HalftonePattern</code> method to decode the pattern. The decoded pattern should be returned in the buffer pointed to by <i>pHTPattern</i>.

You can also use the <code>IPrintOemUni::HalftonePattern</code> method to generate a halftone pattern. In this case an RC_HTPATTERN resource is not needed, so <i>pResource</i> is <b>NULL</b>. The <code>IPrintOemUni::HalftonePattern</code> method should generate a pattern and return it in the buffer pointed to by <i>pHTPattern</i>.

If the <code>IPrintOemUni::HalftonePattern</code> method returns one pattern, it is used for all colors. If the method returns three patterns, they must be specified in RGB order.

The following example shows an implementation of a rendering plug-in's <code>HalftonePattern</code> method. The method calculates the length in bytes of the HTPattern_DDK pattern array, and then copies the bytes in the pattern array to the buffer pointed to by this method's <i>pHTPattern</i> parameter. The pattern array can contain either one or three patterns, depending on whether the pattern is used for all colors or has separate red, green, and blue patterns. For the sake of brevity, not all elements of the pattern array are listed. 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>static BYTE HTPattern_DDK[256] = {
    129,  44,  59, 124, 143, 232, 166, ...
    ...
    ...
    98, 202, 130, 148, 213,  101,  163, 72
};

HRESULT __stdcall IOemUni::HalftonePattern(
    PDEVOBJ     pdevobj,
    PBYTE       pHTPattern,
    DWORD       dwHTPatternX,
    DWORD       dwHTPatternY,
    DWORD       dwHTNumPatterns,
    DWORD       dwCallbackID,
    PBYTE       pResource,
    DWORD       dwResourceSize)
{
PBYTE  pSrcPattern;
DWORD  dwLen = sizeof(HTPattern_DDK);

if (dwLen != (((dwHTPatternX * dwHTPatternY) + 3) / 4) * 4 * dwHTNumPatterns)
 return E_FAIL;

pSrcPattern = HTPattern_DDK;
while (dwLen-- &gt; 0)
 *pHTPattern++ = *pSrcPattern++;

return S_OK;
}</pre>
</td>
</tr>
</table></span></div>An implementation of a <code>HalftonePattern</code> method in the rendering plug-in must be accompanied by a Halftone feature in the GPD file. The following GPD example shows a Halftone feature whose HT_PAT_DDK_16x16 option describes the customized pattern generated in the previous sample. 

*Feature: Halftone

{

    *rcNameID: =HALFTONING_DISPLAY

    *HelpIndex: 12005

    *DefaultOption: HT_PATSIZE_AUTO

    *Option: HT_PATSIZE_AUTO

    {

        *rcNameID: =HT_AUTO_SELECT_DISPLAY

    }

    *Option: HT_PATSIZE_SUPERCELL_M

    {

        *rcNameID: =HT_SUPERCELL_DISPLAY

    }

    *Option: HT_PATSIZE_6x6_M

    {

        *rcNameID: =HT_DITHER6X6_DISPLAY

    }

    *Option: HT_PATSIZE_8x8_M

    {

        *rcNameID: =HT_DITHER8X8_DISPLAY

    }

    *Option: HT_PAT_DDK_16x16

    {

        *Name: "DDK 16x16"

        *HTPatternSize: PAIR(16, 16)

        *HTNumPatterns: 1

        *HTCallbackID: 1

    }

}

The <code>IPrintOemUni::HalftonePattern</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "HalftonePattern" as input.

For more information about halftoning, see <a href="https://msdn.microsoft.com/cc14ff92-743b-42ca-b70f-0df768762f01">Customized Halftoning</a> and <a href="https://msdn.microsoft.com/a188908a-ddf7-4b4d-a46d-e3550ffb0418">Option Attributes for the Halftone Feature</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::HalftonePattern method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

