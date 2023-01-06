---
UID: NF:prcomoem.IPrintOemUni.FilterGraphics
title: IPrintOemUni::FilterGraphics (prcomoem.h)
description: The IPrintOemUni::FilterGraphics method can be used with Unidrv-supported printers to modify scan line data and send it to the spooler.
tech.root: print
ms.date: 01/04/2023
keywords: ["IPrintOemUni::FilterGraphics"]
ms.keywords: FilterGraphics, FilterGraphics method [Print Devices], FilterGraphics method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],FilterGraphics method, IPrintOemUni.FilterGraphics, IPrintOemUni::FilterGraphics, prcomoem/IPrintOemUni::FilterGraphics, print.iprintoemuni_filtergraphics, print_unidrv-pscript_rendering_7e6c6ada-fa4a-4188-b7c2-0ac95869bcdc.xml
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
 - IPrintOemUni::FilterGraphics
 - prcomoem/IPrintOemUni::FilterGraphics
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUni::FilterGraphics
---

## -description

The **IPrintOemUni::FilterGraphics** method can be used with Unidrv-supported printers to modify scan line data and send it to the spooler.

## -parameters

### -param pdevobj

Caller-supplied pointer to a [DEVOBJ](/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj) structure.

### -param pBuf

Caller-supplied pointer to a buffer containing scan line data to be printed.

### -param dwLen

Caller-supplied value representing the length, in bytes, of the data pointed to by *pBuf*.

## -returns

The method must return one of the following values:

| Return code | Description |
|---|---|
| **S_OK** | The operation succeeded. |
| **E_FAIL** | The operation failed |
| **E_NOTIMPL** | The method is not implemented. |

## -remarks

The **IPrintOemUni::FilterGraphics** method is used to modify scan line data before it is sent to the print spooler. The method is responsible for sending the data it receives to the spooler.

The **IPrintOemUni::FilterGraphics** method is optional. If a rendering plug-in implements this method, the plug-in's [IPrintOemUni::GetImplementedMethod](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod) method must return S_OK when it receives "FilterGraphics" as input.

If the **IPrintOemUni::FilterGraphics** method is implemented, Unidrv does not spool printer data. Instead, Unidrv calls this method each time a buffer of image data is ready to be spooled.

Note that when this method is implemented, Unidrv also does not compress printer data, as it normally does. If you intend to make use of Unidrv compression, you should not implement this method. Also, you should modify **IPrintOemUni::GetImplementedMethod** so that it returns S_FALSE when it is passed the string "FilterGraphics".

The method can perform final postprocessing of image data, such as removing adjacent dots or any other data stream filtering operation that Unidrv does not provide. It must then spool the data by calling the [IPrintOemDriverUni::DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf) method.

**IPrintOemUni::FilterGraphics** method is called by Unidrv's [DrvSendPage](/windows/win32/api/winddi/nf-winddi-drvsendpage) function. If you want to implement **IPrintOemUni::FilterGraphics**, you must not completely override Unidrv's **DrvSendPage** or [DrvNextBand](/windows/win32/api/winddi/nf-winddi-drvnextband) functions.

Before Unidrv's **DrvSendPage** function calls the plug-in's **IPrintOemUni::FilterGraphics** implementation, **DrvSendPage**.

1. If necessary, transposes the bitmap that is to be rendered.

1. Transforms an output pass that consists of color data into a single contiguous array of data.

1. Processes a group of scan lines and turn this data into commands for the printer.

1. Sets X/Y position and passes the line of graphics data to the printer.

If the plug-in has implemented **IPrintOemUni::FilterGraphics,** Unidrv will call the plug-in with the scan line data instead of sending it to the printer.

The **IPrintOemUni::FilterGraphics** method allows a rendering plug-in to modify scan line data and send it to the spooler. If you implement this function, Unidrv will not spool your data. Instead, **IPrintOemUni::FilterGraphics** will be called every time a buffer of data is ready to be spooled and sent to the printer.

You can use **IPrintOemUni::FilterGraphics**  to implement a special compression method or to perform bit manipulation on the data stream that is sent to the printer or both. In any situation, the driver's built-in compression code is not used. **IPrintOemUni::FilterGraphics** is presented with a block of data and is required to output this data by using the [DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvwritespoolbuf) function. The core driver (Unidrv) will perform no further processing of the raster data after calling [OEMFilterGraphics](/windows-hardware/drivers/ddi/printoem/nf-printoem-oemfiltergraphics).

When you implement the **IPrintOemUni::FilterGraphics** method in your plug-in, it will be used for sending the raster data directly to the printer. The number of scan lines in a block is specified through the **PinsPerPhysPass** attribute that is associated with the [Resolution feature](/windows-hardware/drivers/print/option-attributes-for-the-resolution-feature) This attribute is optional, and if you do not specify it, it is set to 1 (like it is for most of the inkjet and page printers). Otherwise, **PinsPerPhysPass** should be a multiple of 8. In **IPrintOemUni::FilterGraphics**, the *pBuf* parameter points to the buffer that contains the scan line raster data that you will manipulate if necessary (for example, for compression) and finally send out. The *dwLen* parameter is the length of the buffer that *pBuf* points to.  

The following list describes several common scenarios for implementing **IPrintOemUni::FilterGraphics**:

- Special compression techniques

- Bit manipulation of the incoming raster data before sending it out to the printer

**IPrintOemUni::FilterGraphics** finally sends all of the data to the printer by using the [DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvwritespoolbuf) function. The core driver (Unidrv) does not do any more processing on the data that **IPrintOemUni::FilterGraphics** sends out. If the plug-in is performing special compression or bit manipulation, the plug-in must allocate the buffers that are necessary for the special compression or bit manipulation. If the plug-in does not allocate its own buffers and if the compressed data is smaller than the source, the output will overwrite the source buffer.

The **IPrintOemUni::FilterGraphics** method gives you access to the scan line data itself and gives you the ability to post-process the raster data.

The number of scan lines is equal to the height of the image. For example, a 1 bit per pixel (bpp) thickness of each scan line is equal to the  width of 1 pixel, so the number of scan lines is equal to the height of the image.

For more information about customizing Unidrv's rendering operations, see [Unidrv-Specific Customized Rendering](/windows-hardware/drivers/print/unidrv-specific-customized-rendering).

## -see-also

[DrvNextBand](/windows/win32/api/winddi/nf-winddi-drvnextband)

[DrvSendPage](/windows/win32/api/winddi/nf-winddi-drvsendpage)

[DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/printoem/nc-printoem-pfn_drvwritespoolbuf)

[IPrintOemDriverUni::DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf)

[IPrintOemUni](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuni)

[IPrintOemUni::GetImplementedMethod](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod)

[OEMFilterGraphics](/windows-hardware/drivers/ddi/printoem/nf-printoem-oemfiltergraphics)
