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
ms.keywords: SVI_MAX, SVI_DESTXREL, printoem/SVI_FONTUNDERLINE, printoem/SVI_DESTYREL, SVI_NEXTFONTID, printoem/SVI_COPIES, printoem/SVI_GRAPHICSXRES, printoem/SVI_DESTXREL, printoem/SVI_GREENVALUE, print.stdvariableindex, printoem/SVI_PAGENUMBER, SVI_HEIGHTINPIXELS, SVI_PHYSPAPERLENGTH, printoem/SVI_DESTX, SVI_DESTX, SVI_CURSORORIGINY, printoem/SVI_PHYSPAPERLENGTH, SVI_PATTERNBRUSH_ID, printoem/SVI_TEXTXRES, printoem/SVI_PATTERNBRUSH_TYPE, _STDVARIABLEINDEX, STDVARIABLEINDEX, SVI_NUMDATABYTES, printoem/SVI_NEXTGLYPH, SVI_NEXTGLYPH, SVI_CURRENTPALETTEINDEX, printoem/SVI_RECTYSIZE, SVI_PATTERNBRUSH_SIZE, SVI_CURRENTFONTID, SVI_DESTY, printoem/SVI_LINEFEEDSPACING, printoem/SVI_PRINTDIRECTION, SVI_GRAYPERCENT, printoem/SVI_NUMDATABYTES, SVI_FONTBOLD, printoem/SVI_PHYSPAPERWIDTH, printoem/SVI_FONTBOLD, SVI_PATTERNBRUSH_TYPE, printoem/SVI_CURSORORIGINX, SVI_PRINTDIRECTION, printoem/SVI_PATTERNBRUSH_SIZE, printoem/SVI_MAX, printoem/SVI_GRAYPERCENT, printoem/SVI_CURRENTFONTID, printoem/SVI_HEIGHTINPIXELS, SVI_BLUEVALUE, printoem/SVI_FONTWIDTH, printoem/SVI_FONTSTRIKETHRU, printoem/SVI_FONTHEIGHT, SVI_ROP3, SVI_PALETTEINDEXTOPROGRAM, SVI_PHYSPAPERWIDTH, SVI_REDVALUE, SVI_FONTSTRIKETHRU, SVI_DESTYREL, printoem/SVI_NEXTFONTID, SVI_TEXTXRES, printoem/SVI_FONTITALIC, printoem/SVI_CURSORORIGINY, printoem/SVI_TEXTYRES, printoem/SVI_ROP3, SVI_GRAPHICSYRES, printoem/SVI_REDVALUE, printoem/SVI_PATTERNBRUSH_ID, printoem/SVI_DESTY, SVI_CURSORORIGINX, SVI_RECTXSIZE, printoem/STDVARIABLEINDEX, SVI_FONTUNDERLINE, SVI_PAGENUMBER, SVI_FONTMAXWIDTH, SVI_WIDTHINBYTES, printoem/SVI_PALETTEINDEXTOPROGRAM, STDVARIABLEINDEX enumeration [Print Devices], printoem/SVI_FONTMAXWIDTH, SVI_TEXTYRES, SVI_FONTHEIGHT, SVI_GREENVALUE, printoem/SVI_RECTXSIZE, SVI_GRAPHICSXRES, printoem/SVI_GRAPHICSYRES, printoem/SVI_WIDTHINBYTES, SVI_LINEFEEDSPACING, SVI_RECTYSIZE, printoem/SVI_CURRENTPALETTEINDEX, SVI_FONTWIDTH, printoem/SVI_BLUEVALUE, SVI_COPIES, SVI_FONTITALIC
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




#### - SVI_NUMDATABYTES

The number of data bytes.


#### - SVI_WIDTHINBYTES

The raster data width in bytes.


#### - SVI_HEIGHTINPIXELS

The raster data height in pixels.


#### - SVI_COPIES

The number of copies.


#### - SVI_PRINTDIRECTION

The print direction in CC degrees.


#### - SVI_DESTX

The x destination.


#### - SVI_DESTY

The y destination.


#### - SVI_DESTXREL

The relative x destination.


#### - SVI_DESTYREL

The relative y direction.


#### - SVI_LINEFEEDSPACING

The line feed spacing.


#### - SVI_RECTXSIZE

The x rect size.


#### - SVI_RECTYSIZE

The y rect size.


#### - SVI_GRAYPERCENT

The gray percentage.


#### - SVI_NEXTFONTID

The next font ID.


#### - SVI_NEXTGLYPH

The next glyph.


#### - SVI_PHYSPAPERLENGTH

The physical paper length.


#### - SVI_PHYSPAPERWIDTH

The physical paper width.


#### - SVI_FONTHEIGHT

The font height.


#### - SVI_FONTWIDTH

The font width.


#### - SVI_FONTMAXWIDTH

The max font width.


#### - SVI_FONTBOLD

The font is bold.


#### - SVI_FONTITALIC

The font is italicized.


#### - SVI_FONTUNDERLINE

The font is underlined.


#### - SVI_FONTSTRIKETHRU

The font has the strikethru style applied.


#### - SVI_CURRENTFONTID

The current font ID.


#### - SVI_TEXTYRES

The text y resolution.


#### - SVI_TEXTXRES

The text x resolution.


#### - SVI_GRAPHICSYRES

The graphics y resolution.


#### - SVI_GRAPHICSXRES

The graphics x resolution.


#### - SVI_ROP3

The rop3.


#### - SVI_REDVALUE

The red value.


#### - SVI_GREENVALUE

The green value.


#### - SVI_BLUEVALUE

The blue value.


#### - SVI_PALETTEINDEXTOPROGRAM

The palette index to program.


#### - SVI_CURRENTPALETTEINDEX

The current palette index.


#### - SVI_PATTERNBRUSH_TYPE

The pattern brush type.


#### - SVI_PATTERNBRUSH_ID

The pattern brush ID.


#### - SVI_PATTERNBRUSH_SIZE

The pattern brush size.


#### - SVI_CURSORORIGINX

The cursor origin x value. This is in master units and in the coordinates of the currently selected orientation. This values is defined as ImageableOrigin minus CursorOrigin.


#### - SVI_CURSORORIGINY

The cursor origin y value. This is in master units and in the coordinates of the currently selected orientation. This values is defined as ImageableOrigin minus CursorOrigin.


#### - SVI_PAGENUMBER

The page number. This value tracks the number of times DrvStartBand has been called since StartDoc.


#### - SVI_MAX

Placeholder. Do not use.

