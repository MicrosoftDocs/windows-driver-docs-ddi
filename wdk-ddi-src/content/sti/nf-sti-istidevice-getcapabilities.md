---
UID: NF:sti.IStiDevice.GetCapabilities
title: IStiDevice::GetCapabilities (sti.h)
description: The IStiDevice::GetCapabilities method returns a still image device's capabilities.
old-location: image\istidevice_getcapabilities.htm
tech.root: image
ms.assetid: 4c5d8834-a78d-443e-bfec-1d9fcddb9331
ms.date: 05/03/2018
keywords: ["IStiDevice::GetCapabilities"]
ms.keywords: GetCapabilities, GetCapabilities method [Imaging Devices], GetCapabilities method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],GetCapabilities method, IStiDevice.GetCapabilities, IStiDevice::GetCapabilities, image.istidevice_getcapabilities, sti/IStiDevice::GetCapabilities, stifnc_00882aa7-e8cd-4218-9d05-b9d1f56a6652.xml
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
 - IStiDevice::GetCapabilities
 - sti/IStiDevice::GetCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.GetCapabilities
---

# IStiDevice::GetCapabilities


## -description

The <b>IStiDevice::GetCapabilities</b> method returns a still image device's capabilities.

## -parameters

### -param pDevCaps 

[in, out]
Caller-supplied pointer to an empty <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_sti_dev_caps">STI_DEV_CAPS</a> structure.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDevice::GetCapabilities</b> method returns device capability flags in the caller-supplied <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_sti_dev_caps">STI_DEV_CAPS</a> structure.

Before calling <b>IStiDevice::GetCapabilities</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.