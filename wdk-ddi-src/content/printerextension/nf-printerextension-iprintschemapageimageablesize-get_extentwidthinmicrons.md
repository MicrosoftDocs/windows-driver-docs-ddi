---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons
title: IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons method
author: windows-driver-content
description: Gets the horizontal distance between the origin and the bounding limit of the application media size.
old-location: print\iprintschemapageimageablesize_extentwidthinmicrons.htm
old-project: print
ms.assetid: B30CD277-ADE2-45F7-BE73-CF738843D9B9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, E, ExtentWidthInMicrons property [Print Devices], ExtentWidthInMicrons property [Print Devices], IPrintSchemaPageImageableSize interface, I, IPrintSchemaPageImageableSize, IPrintSchemaPageImageableSize interface [Print Devices], ExtentWidthInMicrons property, IPrintSchemaPageImageableSize.ExtentWidthInMicrons, IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons, M, P, S, W, _, a, b, c, d, e, g, get_ExtentWidthInMicrons, get_ExtentWidthInMicrons,IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons, h, i, l, m, n, o, print.iprintschemapageimageablesize_extentwidthinmicrons, printerextension/IPrintSchemaPageImageableSize::ExtentWidthInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons, r, s, t, x, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaPageImageableSize.ExtentWidthInMicrons
-	IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons method


## -description


Gets the horizontal distance between the origin and the bounding limit of the application media size.

This property is read-only.


## -syntax


````
HRESULT get_ExtentWidthInMicrons(
  [out, retval] ULONG *pulExtentWidth
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemapageimageablesize.md">IPrintSchemaPageImageableSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaPageImageableSize::ExtentWidthInMicrons property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

