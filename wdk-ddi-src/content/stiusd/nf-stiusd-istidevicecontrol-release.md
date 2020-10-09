---
UID: NF:stiusd.IStiDeviceControl.Release
title: IStiDeviceControl::Release (stiusd.h)
description: The IStiDeviceControl::Release method closes the instance of the COM object that was created when a minidriver client called IStiUSD::Initialize.
old-location: image\istidevicecontrol_release.htm
tech.root: image
ms.assetid: 56c2ddc0-9f25-4d4f-9f6e-d8c96c9acc91
ms.date: 05/03/2018
keywords: ["IStiDeviceControl::Release"]
ms.keywords: IStiDeviceControl interface [Imaging Devices],Release method, IStiDeviceControl.Release, IStiDeviceControl::Release, Release, Release method [Imaging Devices], Release method [Imaging Devices],IStiDeviceControl interface, image.istidevicecontrol_release, stifnc_c0e50ea5-46e3-4b30-92b4-be6906647671.xml, stiusd/IStiDeviceControl::Release
req.header: stiusd.h
req.include-header: Stiusd.h
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
 - IStiDeviceControl::Release
 - stiusd/IStiDeviceControl::Release
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Stiusd.h
api_name:
 - IStiDeviceControl.Release
---

# IStiDeviceControl::Release


## -description

The <b>IStiDeviceControl::Release</b> method closes the instance of the COM object that was created when a minidriver client called <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a>.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.

## -remarks

The <b>IStiDeviceControl::Release</b> method should be called from within the destructor function of a user-mode still image minidriver's <b>IStiUSD</b> interface. (For more information, see <a href="/windows-hardware/drivers/image/creating-a-user-mode-still-image-minidriver">Creating a User-Mode Still Image Minidriver</a>.)

A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as input to its <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/_image/index">IStiDeviceControl</a>



<a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-addref">IStiDeviceControl::AddRef</a>