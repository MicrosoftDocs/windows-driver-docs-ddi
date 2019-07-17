---
UID: NF:prcomoem.IPrintOemUni.HalftonePattern
title: IPrintOemUni::HalftonePattern (prcomoem.h)
description: The IPrintOemUni::HalftonePattern method can be used with Unidrv-supported printers to create or modify a halftone pattern before it is used in a halftoning operation.
old-location: print\iprintoemuni_halftonepattern.htm
tech.root: print
ms.assetid: 1b899492-f4a7-4c13-9e19-0f086b2b6b47
ms.date: 04/20/2018
ms.keywords: HalftonePattern, HalftonePattern method [Print Devices], HalftonePattern method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],HalftonePattern method, IPrintOemUni.HalftonePattern, IPrintOemUni::HalftonePattern, prcomoem/IPrintOemUni::HalftonePattern, print.iprintoemuni_halftonepattern, print_unidrv-pscript_rendering_672da2b9-981c-4c4c-a303-88377fe01741.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintOemUni.HalftonePattern"
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
- IPrintOemUni.HalftonePattern
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::HalftonePattern

## -description

The **IPrintOemUni::HalftonePattern** method can be used with Unidrv-supported printers to create or modify a halftone pattern before it is used in a halftoning operation.

## -parameters

### -param pdevobj

Caller-supplied pointer to a [DEVOBJ](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj) structure.

### -param pHTPattern

Caller-supplied pointer to a buffer that receives the method-supplied halftone pattern. Buffer size, in bytes, is:

`(((dwHTPatternX * dwHTPatternY) + 3)/4) * 4 * dwHTNumPatterns`

### -param dwHTPatternX

Caller-supplied length, in pixels, of the halftone pattern, as specified by the first value in the GPD file's ***HTPatternSize** attribute.

### -param dwHTPatternY

Caller-supplied height, in pixels, of the halftone pattern, as specified by the second value in the GPD file's ***HTPatternSize** attribute.

### -param dwHTNumPatterns

Caller-supplied number of patterns, as specified by the GPD file's ***HTNumPatterns** attribute. The number of patterns can be either 1 or 3.

### -param dwCallbackID

Caller-supplied value identifying the halftone method, as specified by the GPD file's ***HTCallbackID** attribute.

### -param pResource

Caller-supplied pointer to a buffer containing a halftone pattern, as specified by the GPD file's ***rcHTPatternID** attribute. This can be **NULL**.

### -param dwResourceSize

Caller-supplied size of the halftone pattern contained in the buffer pointed to by *pResource*. This is zero if *pResource* is **NULL**.

## -returns

The method must return one of the following values:

| Return code | Description |
| --- | --- |
| S_OK | The operation succeeded. |
| E_FAIL | The operation failed. |
| E_NOTIMPL | The method is not implemented. |

## -remarks

The **IPrintOemUni::HalftonePattern** method is used to create or modify a halftone pattern before Unidrv passes it to GDI. Its purpose is to allow proprietary halftone patterns to be either stored as encrypted resources or generated at run time.

If the **IPrintOemUni::HalftonePattern** method is implemented, and if the GPD file entry for the currently selected halftoning method includes an ***HTCallbackID** attribute, Unidrv calls the **IPrintOemUni::HalftonePattern** method before passing a halftone pattern to GDI.

If the GPD file entry for the currently selected halftoning method contains an *rcHTPatternID entry identifying an RC_HTPATTERN resource, Unidrv obtains the pattern and passes a pointer to it as the *pResource* parameter value. This allows you to store the pattern as an encrypted resource, and to use the **IPrintOemUni::HalftonePattern** method to decode the pattern. The decoded pattern should be returned in the buffer pointed to by *pHTPattern*.

You can also use the **IPrintOemUni::HalftonePattern** method to generate a halftone pattern. In this case an RC_HTPATTERN resource is not needed, so *pResource* is **NULL**. The **IPrintOemUni::HalftonePattern** method should generate a pattern and return it in the buffer pointed to by *pHTPattern*.

If the **IPrintOemUni::HalftonePattern** method returns one pattern, it is used for all colors. If the method returns three patterns, they must be specified in RGB order.

The following example shows an implementation of a rendering plug-in's **HalftonePattern** method. The method calculates the length in bytes of the HTPattern_DDK pattern array, and then copies the bytes in the pattern array to the buffer pointed to by this method's *pHTPattern* parameter. The pattern array can contain either one or three patterns, depending on whether the pattern is used for all colors or has separate red, green, and blue patterns. For the sake of brevity, not all elements of the pattern array are listed.

```cpp
static BYTE HTPattern_DDK[256] = {
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

while (dwLen-- > 0)
    *pHTPattern++ = *pSrcPattern++;

return S_OK;
}
```

An implementation of a **HalftonePattern** method in the rendering plug-in must be accompanied by a Halftone feature in the GPD file. The following GPD example shows a Halftone feature whose HT_PAT_DDK_16x16 option describes the customized pattern generated in the previous sample.

```GPD

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
```

The **IPrintOemUni::HalftonePattern** method is optional. If a rendering plug-in implements this method, the plug-in's [IPrintOemUni::GetImplementedMethod](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod) method must return S_OK when it receives "HalftonePattern" as input.

For more information about halftoning, see [Customized Halftoning](https://docs.microsoft.com/windows-hardware/drivers/print/customized-halftoning) and [Option Attributes for the Halftone Feature](https://docs.microsoft.com/windows-hardware/drivers/print/option-attributes-for-the-halftone-feature).

## -see-also

[IPrintOemUni Interface](https://docs.microsoft.com/windows-hardware/drivers/print/iprintoemuni-com-interface)

[IPrintOemUni::ImageProcessing](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing)
