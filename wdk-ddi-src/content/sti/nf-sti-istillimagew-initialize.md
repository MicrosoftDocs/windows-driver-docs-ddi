---
UID: NF:sti.IStillImageW.Initialize
title: IStillImageW::Initialize (sti.h)
description: The IStillImage::Initialize method initializes an instance of the COM object that defines the IStillImage COM interface. This method is for internal system use only.
old-location: image\istillimage_initialize.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStillImageW::Initialize"]
ms.keywords: IStillImageW interface [Imaging Devices],Initialize method, IStillImageW.Initialize, IStillImageW::Initialize, Initialize, Initialize method [Imaging Devices], Initialize method [Imaging Devices],IStillImageW interface, image.istillimage_initialize, sti/IStillImageW::Initialize, stifnc_31e54f97-84af-47bf-a1b1-17ab697caef3.xml
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IStillImageW::Initialize
 - sti/IStillImageW::Initialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::Initialize
---

# IStillImageW::Initialize


## -description

The <b>IStillImage::Initialize</b> method initializes an instance of the COM object that defines the <b>IStillImage</b> COM interface. <i>This method is for internal system use only</i>.

## -parameters

### -param hinst 

[in]
Caller-supplied instance handle of the calling process. This handle is obtained by calling <b>GetModuleName</b>(NULL).

### -param dwVersion

Caller-supplied STI version number. This value must be STI_VERSION, defined in <i>Sti.h</i>.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h.</i>

## -remarks

The <b>IStillImage::Initialize</b> method initializes the COM object instance that was created by calling <a href="/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a>.

Because <b>IStillImage::Initialize</b> is called by <b>IStillImage::StiCreateInstance</b>, clients of the <b>IStillImage</b> COM interface do not typically call this method directly.

