---
UID: NF:stiusd.IStiDeviceControl.AddRef
title: IStiDeviceControl::AddRef (stiusd.h)
description: The IStiDeviceControl::AddRef method increments the reference count for the IStiDeviceControl interface.
old-location: image\istidevicecontrol_addref.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStiDeviceControl::AddRef"]
ms.keywords: AddRef, AddRef method [Imaging Devices], AddRef method [Imaging Devices],IStiDeviceControl interface, IStiDeviceControl interface [Imaging Devices],AddRef method, IStiDeviceControl.AddRef, IStiDeviceControl::AddRef, image.istidevicecontrol_addref, stifnc_b0cd1dfe-9e37-42a5-83e0-d0f97c9439e8.xml, stiusd/IStiDeviceControl::AddRef
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
 - IStiDeviceControl::AddRef
 - stiusd/IStiDeviceControl::AddRef
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Stiusd.h
api_name:
 - IStiDeviceControl.AddRef
---

# IStiDeviceControl::AddRef


## -description

The <b>IStiDeviceControl::AddRef</b> method increments the reference count for the <b>IStiDeviceControl</b> interface.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDeviceControl::AddRef</b> method should be called from within a user-mode still image minidriver's <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a> method.

A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as an input argument to its <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/_image/index">IStiDeviceControl</a>



<a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-release">IStiDeviceControl::Release</a>
