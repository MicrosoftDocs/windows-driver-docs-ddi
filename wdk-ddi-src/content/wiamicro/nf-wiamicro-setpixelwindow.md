---
UID: NF:wiamicro.SetPixelWindow
title: SetPixelWindow function
author: windows-driver-content
description: The SetPixelWindow function sets the image area to be scanned.
old-location: image\setpixelwindow.htm
old-project: Image
ms.assetid: e1b5af5d-9bb8-4bf0-898a-5972f1f09a35
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SetPixelWindow, SetPixelWindow function [Imaging Devices], MicroDrv_45542a77-e61e-49ba-a9f3-df7d8dd57402.xml, image.setpixelwindow, wiamicro/SetPixelWindow
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamicro.h
apiname:
-	SetPixelWindow
product: Windows
targetos: Windows
req.typenames: "*PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# SetPixelWindow function


## -description


The <b>SetPixelWindow </b>function sets the image area to be scanned.


## -syntax


````
WIAMICRO_API HRESULT SetPixelWindow(
  _Inout_ PSCANINFO pScanInfo,
          LONG      x,
          LONG      y,
          LONG      xExtent,
          LONG      yExtent
);
````


## -parameters




### -param pScanInfo [in, out]

Points to a <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure that represents the current state of the device. This is stored by the WIA Flatbed driver to guarantee synchronized settings between the microdriver and the WIA Flatbed driver.


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



In this function, the microdriver should set up the <b>Window</b> member of the <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure, making any device-specific adjustments that are necessary. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552722">WIA Microdriver Structures</a>



<a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20SetPixelWindow function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

