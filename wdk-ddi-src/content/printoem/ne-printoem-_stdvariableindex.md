---
UID: NE:printoem._STDVARIABLEINDEX
title: "_STDVARIABLEINDEX"
author: windows-driver-content
description: "."
old-location: print\stdvariableindex.htm
old-project: print
ms.assetid: 02E54636-0B8D-40FE-8405-0FB130139828
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: printoem/SVI_ROP3, printoem/SVI_GRAPHICSYRES, printoem/SVI_WIDTHINBYTES, SVI_CURRENTPALETTEINDEX, printoem/SVI_PHYSPAPERWIDTH, printoem/SVI_TEXTXRES, printoem/SVI_FONTBOLD, printoem/SVI_MAX, SVI_WIDTHINBYTES, SVI_DESTX, printoem/SVI_FONTITALIC, printoem/SVI_DESTYREL, printoem/SVI_FONTWIDTH, SVI_FONTBOLD, printoem/SVI_FONTMAXWIDTH, printoem/SVI_PATTERNBRUSH_SIZE, printoem/SVI_FONTUNDERLINE, printoem/STDVARIABLEINDEX, SVI_FONTITALIC, printoem/SVI_PATTERNBRUSH_TYPE, SVI_PALETTEINDEXTOPROGRAM, printoem/SVI_GRAPHICSXRES, SVI_PHYSPAPERWIDTH, SVI_LINEFEEDSPACING, printoem/SVI_COPIES, printoem/SVI_PAGENUMBER, SVI_PATTERNBRUSH_SIZE, SVI_CURSORORIGINX, SVI_DESTXREL, printoem/SVI_FONTHEIGHT, SVI_GRAPHICSXRES, printoem/SVI_DESTY, SVI_PATTERNBRUSH_TYPE, printoem/SVI_CURSORORIGINX, SVI_TEXTYRES, printoem/SVI_LINEFEEDSPACING, printoem/SVI_DESTX, SVI_TEXTXRES, STDVARIABLEINDEX, SVI_CURRENTFONTID, SVI_DESTYREL, STDVARIABLEINDEX enumeration [Print Devices], SVI_GRAYPERCENT, SVI_PRINTDIRECTION, SVI_RECTYSIZE, SVI_GREENVALUE, printoem/SVI_CURRENTFONTID, printoem/SVI_HEIGHTINPIXELS, printoem/SVI_PHYSPAPERLENGTH, printoem/SVI_PATTERNBRUSH_ID, SVI_NUMDATABYTES, SVI_NEXTGLYPH, SVI_FONTSTRIKETHRU, printoem/SVI_GREENVALUE, printoem/SVI_RECTXSIZE, printoem/SVI_PRINTDIRECTION, printoem/SVI_GRAYPERCENT, _STDVARIABLEINDEX, SVI_COPIES, SVI_CURSORORIGINY, SVI_MAX, printoem/SVI_FONTSTRIKETHRU, printoem/SVI_BLUEVALUE, SVI_DESTY, printoem/SVI_PALETTEINDEXTOPROGRAM, printoem/SVI_REDVALUE, SVI_ROP3, SVI_FONTMAXWIDTH, SVI_PHYSPAPERLENGTH, printoem/SVI_NEXTFONTID, SVI_FONTHEIGHT, printoem/SVI_RECTYSIZE, SVI_HEIGHTINPIXELS, SVI_GRAPHICSYRES, printoem/SVI_CURRENTPALETTEINDEX, SVI_RECTXSIZE, SVI_FONTWIDTH, SVI_REDVALUE, SVI_BLUEVALUE, SVI_PAGENUMBER, print.stdvariableindex, printoem/SVI_TEXTYRES, SVI_FONTUNDERLINE, SVI_NEXTFONTID, printoem/SVI_NUMDATABYTES, printoem/SVI_NEXTGLYPH, SVI_PATTERNBRUSH_ID, printoem/SVI_DESTXREL, printoem/SVI_CURSORORIGINY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printoem.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Printoem.h
apiname:
-	STDVARIABLEINDEX
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# _STDVARIABLEINDEX enumeration


## -description





## -syntax


````
typedef enum _STDVARIABLEINDEX { 
  SVI_NUMDATABYTES,
  SVI_WIDTHINBYTES,
  SVI_HEIGHTINPIXELS,
  SVI_COPIES,
  SVI_PRINTDIRECTION,
  SVI_DESTX,
  SVI_DESTY,
  SVI_DESTXREL,
  SVI_DESTYREL,
  SVI_LINEFEEDSPACING,
  SVI_RECTXSIZE,
  SVI_RECTYSIZE,
  SVI_GRAYPERCENT,
  SVI_NEXTFONTID,
  SVI_NEXTGLYPH,
  SVI_PHYSPAPERLENGTH,
  SVI_PHYSPAPERWIDTH,
  SVI_FONTHEIGHT,
  SVI_FONTWIDTH,
  SVI_FONTMAXWIDTH,
  SVI_FONTBOLD,
  SVI_FONTITALIC,
  SVI_FONTUNDERLINE,
  SVI_FONTSTRIKETHRU,
  SVI_CURRENTFONTID,
  SVI_TEXTYRES,
  SVI_TEXTXRES,
  SVI_GRAPHICSYRES,
  SVI_GRAPHICSXRES,
  SVI_ROP3,
  SVI_REDVALUE,
  SVI_GREENVALUE,
  SVI_BLUEVALUE,
  SVI_PALETTEINDEXTOPROGRAM,
  SVI_CURRENTPALETTEINDEX,
  SVI_PATTERNBRUSH_TYPE,
  SVI_PATTERNBRUSH_ID,
  SVI_PATTERNBRUSH_SIZE,
  SVI_CURSORORIGINX,
  SVI_CURSORORIGINY,
  SVI_PAGENUMBER,
  SVI_MAX
} STDVARIABLEINDEX;
````


## -enum-fields




### -field SVI_NUMDATABYTES

The number of data bytes.


### -field SVI_WIDTHINBYTES

The raster data width in bytes.


### -field SVI_HEIGHTINPIXELS

The raster data height in pixels.


### -field SVI_COPIES

The number of copies.


### -field SVI_PRINTDIRECTION

The print direction in CC degrees.


### -field SVI_DESTX

The x destination.


### -field SVI_DESTY

The y destination.


### -field SVI_DESTXREL

The relative x destination.


### -field SVI_DESTYREL

The relative y direction.


### -field SVI_LINEFEEDSPACING

The line feed spacing.


### -field SVI_RECTXSIZE

The x rect size.


### -field SVI_RECTYSIZE

The y rect size.


### -field SVI_GRAYPERCENT

The gray percentage.


### -field SVI_NEXTFONTID

The next font ID.


### -field SVI_NEXTGLYPH

The next glyph.


### -field SVI_PHYSPAPERLENGTH

The physical paper length.


### -field SVI_PHYSPAPERWIDTH

The physical paper width.


### -field SVI_FONTHEIGHT

The font height.


### -field SVI_FONTWIDTH

The font width.


### -field SVI_FONTMAXWIDTH

The max font width.


### -field SVI_FONTBOLD

The font is bold.


### -field SVI_FONTITALIC

The font is italicized.


### -field SVI_FONTUNDERLINE

The font is underlined.


### -field SVI_FONTSTRIKETHRU

The font has the strikethru style applied.


### -field SVI_CURRENTFONTID

The current font ID.


### -field SVI_TEXTYRES

The text y resolution.


### -field SVI_TEXTXRES

The text x resolution.


### -field SVI_GRAPHICSYRES

The graphics y resolution.


### -field SVI_GRAPHICSXRES

The graphics x resolution.


### -field SVI_ROP3

The rop3.


### -field SVI_REDVALUE

The red value.


### -field SVI_GREENVALUE

The green value.


### -field SVI_BLUEVALUE

The blue value.


### -field SVI_PALETTEINDEXTOPROGRAM

The palette index to program.


### -field SVI_CURRENTPALETTEINDEX

The current palette index.


### -field SVI_PATTERNBRUSH_TYPE

The pattern brush type.


### -field SVI_PATTERNBRUSH_ID

The pattern brush ID.


### -field SVI_PATTERNBRUSH_SIZE

The pattern brush size.


### -field SVI_CURSORORIGINX

The cursor origin x value. This is in master units and in the coordinates of the currently selected orientation. This values is defined as ImageableOrigin minus CursorOrigin.


### -field SVI_CURSORORIGINY

The cursor origin y value. This is in master units and in the coordinates of the currently selected orientation. This values is defined as ImageableOrigin minus CursorOrigin.


### -field SVI_PAGENUMBER

The page number. This value tracks the number of times DrvStartBand has been called since StartDoc.


### -field SVI_MAX

Placeholder. Do not use.

