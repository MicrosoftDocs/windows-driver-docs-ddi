---
UID: NF:wiautil.CWiauFormatConverter.Init
title: CWiauFormatConverter::Init method
author: windows-driver-content
description: The CWiauFormatConverter::Init method initializes the CWiauFormatConverter class and GDI+ for converting images. This method should be called only once.
old-location: image\cwiauformatconverter_init.htm
old-project: image
ms.assetid: 342ea1ae-ff8c-429d-bee8-08559fe75b40
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauFncs_d762c597-47d1-446a-b76d-7993ba32f571.xml, Init method [Imaging Devices], CWiauFormatConverter interface, image.cwiauformatconverter_init, CWiauFormatConverter, CWiauFormatConverter::Init, Init method [Imaging Devices], CWiauFormatConverter interface [Imaging Devices], Init method, wiautil/CWiauFormatConverter::Init, Init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: wiautil.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	Wiautil.h
apiname: 
-	CWiauFormatConverter.Init
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauFormatConverter::Init method


## -description


The <b>CWiauFormatConverter::Init</b> method initializes the <b>CWiauFormatConverter</b> class and GDI+ for converting images. This method should be called only once.


## -syntax


````
HRESULT Init();
````


## -parameters





## -returns


On success, the function returns S_OK. If the function fails, it returns a standard COM error.


