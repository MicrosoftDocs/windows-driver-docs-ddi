---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ImageableSizeWidthInMicrons
title: IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons method
author: windows-driver-content
description: Gets the horizontal dimension of the application media size relative to the page orientation.
old-location: print\iprintschemapageimageablesize_imageablesizewidthinmicrons.htm
old-project: print
ms.assetid: 46556C6E-B231-400D-8F0A-86FC1CD5D4B6
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: ImageableSizeWidthInMicrons property [Print Devices], IPrintSchemaPageImageableSize interface, IPrintSchemaPageImageableSize.ImageableSizeWidthInMicrons, get_ImageableSizeWidthInMicrons, printerextension/IPrintSchemaPageImageableSize::ImageableSizeWidthInMicrons, IPrintSchemaPageImageableSize interface [Print Devices], ImageableSizeWidthInMicrons property, printerextension/IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons, ImageableSizeWidthInMicrons property [Print Devices], IPrintSchemaPageImageableSize, IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons, print.iprintschemapageimageablesize_imageablesizewidthinmicrons
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
-	IPrintSchemaPageImageableSize.ImageableSizeWidthInMicrons
-	IPrintSchemaPageImageableSize.get_ImageableSizeWidthInMicrons
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons method


## -description


Gets the horizontal dimension of the application media size relative to the page orientation.

This property is read-only.


## -syntax


````
HRESULT get_ImageableSizeWidthInMicrons(
  [out, retval] ULONG *pulImageableSizeWidth
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemapageimageablesize.md">IPrintSchemaPageImageableSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaPageImageableSize::ImageableSizeWidthInMicrons property%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

