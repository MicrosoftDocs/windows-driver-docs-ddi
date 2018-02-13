---
UID: NS:printoem.IPPARAMS
title: IPPARAMS
author: windows-driver-content
description: The IPPARAMS structure is used as an input parameter to a rendering plug-in's IPrintOemUni::ImageProcessing method.
old-location: print\ipparams.htm
old-project: print
ms.assetid: 14ed4180-9ac1-46dd-af76-8d79a2a1fd2d
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: PIPPARAMS structure pointer [Print Devices], printoem/PIPPARAMS, printoem/IPPARAMS, print_unidrv-pscript_rendering_a002bc49-f3de-4147-bb33-8766672c8d0c.xml, IPPARAMS, IPPARAMS structure [Print Devices], *PIPPARAMS, PIPPARAMS, print.ipparams
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
apiname:
-	IPPARAMS
product: Windows
targetos: Windows
req.typenames: "*PIPPARAMS, IPPARAMS"
req.product: Windows 10 or later.
---

# IPPARAMS structure


## -description


The IPPARAMS structure is used as an input parameter to a rendering plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a> method.


## -syntax


````
typedef struct {
  DWORD dwSize;
  POINT ptOffset;
  PSTR  pHalftoneOption;
  BOOL  bBanding;
  BOOL  bBlankBand;
} IPPARAMS, *PIPPARAMS;
````


## -struct-fields




### -field dwSize

Specifies the size, in bytes of the IPPARAMS structure. Supplied by Unidrv.


### -field ptOffset

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a> structure containing the banded image's offset from the upper left corner of the drawing area. Supplied by Unidrv.


### -field pHalftoneOption

Pointer to a string containing the name of the currently selected halftoning option. Supplied by Unidrv.


### -field bBanding

Specifies whether image banding is active. If <b>TRUE</b>, image banding is active. If <b>FALSE</b>, image banding is not active. Supplied by Unidrv.


### -field bBlankBand

Specifies whether a blank band was drawn in the source bitmap supplied to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>. A value of <b>TRUE</b> indicates that nothing was drawn in the source bitmap supplied to <b>IPrintOemUni::ImageProcessing</b>. A <b>TRUE</b> value also indicates that data in the source bitmap is invalid and should not be processed. Supplied by Unidrv.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPPARAMS structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

