---
UID: NF:sti.IStillImageW.Initialize
title: IStillImageW::Initialize method
author: windows-driver-content
description: The IStillImage::Initialize method initializes an instance of the COM object that defines the IStillImage COM interface. This method is for internal system use only.
old-location: image\istillimage_initialize.htm
old-project: image
ms.assetid: 2410f27f-f880-4870-a86a-2d6000b651fd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, I, IStillImageW, IStillImageW interface [Imaging Devices], Initialize method, IStillImageW::Initialize, Initialize method [Imaging Devices], Initialize method [Imaging Devices], IStillImageW interface, Initialize,IStillImageW.Initialize, S, W, a, e, g, i, image.istillimage_initialize, l, m, n, sti/IStillImageW::Initialize, stifnc_31e54f97-84af-47bf-a1b1-17ab697caef3.xml, t, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStillImageW.Initialize
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::Initialize method


## -description


The <b>IStillImage::Initialize</b> method initializes an instance of the COM object that defines the <b>IStillImage</b> COM interface. <i>This method is for internal system use only</i>.


## -syntax


````
HRESULT Initialize(
  [in] HINSTANCE hinst,
       DWORD     dwVersion
);
````


## -parameters




### -param hinst [in]

Caller-supplied instance handle of the calling process. This handle is obtained by calling <b>GetModuleName</b>(NULL).


### -param dwVersion

Caller-supplied STI version number. This value must be STI_VERSION, defined in <i>Sti.h</i>.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h.</i>




## -remarks



The <b>IStillImage::Initialize</b> method initializes the COM object instance that was created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a>.

Because <b>IStillImage::Initialize</b> is called by <b>IStillImage::StiCreateInstance</b>, clients of the <b>IStillImage</b> COM interface do not typically call this method directly.



