---
UID: NF:wiamicro.SetPixelWindow
title: SetPixelWindow function (wiamicro.h)
description: The SetPixelWindow function sets the image area to be scanned.
old-location: image\setpixelwindow.htm
tech.root: image
ms.assetid: e1b5af5d-9bb8-4bf0-898a-5972f1f09a35
ms.date: 05/03/2018
keywords: ["SetPixelWindow function"]
ms.keywords: MicroDrv_45542a77-e61e-49ba-a9f3-df7d8dd57402.xml, SetPixelWindow, SetPixelWindow function [Imaging Devices], image.setpixelwindow, wiamicro/SetPixelWindow
f1_keywords:
 - "wiamicro/SetPixelWindow"
req.header: wiamicro.h
req.include-header: Wiamicro.h
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
- HeaderDef
api_location:
- wiamicro.h
api_name:
- SetPixelWindow
product:
- Windows
targetos: Windows
req.typenames: 
---

# SetPixelWindow function

## -description

The **SetPixelWindow** function sets the image area to be scanned.

## -parameters

### -param pScanInfo [in, out]

Points to a [SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo) structure that represents the current state of the device. This is stored by the WIA Flatbed driver to guarantee synchronized settings between the microdriver and the WIA Flatbed driver.

### -param x

Specifies the horizontal position value for the left side of the selection rectangle in pixels.

### -param y

Specifies the vertical position value for the top of the selection rectangle in pixels.

### -param xExtent

Specifies the width of the selection rectangle in pixels.

### -param yExtent

Specifies the height of the selection rectangle in pixels.

## -returns

If the function succeeds, it returns S_OK. If the function fails, it returns a standard COM error code.

## -remarks

In this function, the microdriver should set up the **Window** member of the [SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo) structure, making any device-specific adjustments that are necessary.

## -see-also

[SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo)

[WIA Microdriver Structures](https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index)
