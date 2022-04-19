---
UID: NF:stiusd.IStiUSD.Escape
title: IStiUSD::Escape (stiusd.h)
description: A still image minidriver's IStiUSD::Escape method performs a vendor-specific I/O operation on a still image device.
tech.root: image
ms.date: 04/19/2022
keywords: ["IStiUSD::Escape"]
ms.keywords: Escape, Escape method [Imaging Devices], Escape method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],Escape method, IStiUSD.Escape, IStiUSD::Escape, image.istiusd_escape, stifnc_74a53282-ebd8-4c87-97b1-58195b40a1af.xml, stiusd/IStiUSD::Escape
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
 - IStiUSD::Escape
 - stiusd/IStiUSD::Escape
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD::Escape
---

## -description

A still image minidriver's **IStiUSD::Escape** method performs a vendor-specific I/O operation on a still image device.

## -parameters

### -param EscapeFunction

Caller-supplied, vendor-defined, DWORD-sized value representing an I/O operation. Vendor-defined values must be greater than STI_RAW_RESERVED, which is defined in *Sti.h*.

### -param lpInData

Caller-supplied pointer to a buffer containing data sent to the device.

### -param cbInDataSize

Caller-supplied length, in bytes, of the buffer pointed to by *lpInData*.

### -param pOutData

Caller-supplied pointer to a memory buffer to receive data from the device.

### -param cbOutDataSize

Caller-supplied length, in bytes, of the buffer pointed to by *lpOutData*.

### -param pdwActualData

Receives the number of bytes actually written to *pOutData*.

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in *stierr.h*. If the method is not implemented, it should return STIERR_UNSUPPORTED.

## -remarks

A still image minidriver only needs to implement **IStiUSD::Escape** if I/O operations are required that cannot be implemented within [IStiUSD::RawReadData](/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawreaddata), [IStiUSD::RawWriteData](/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawwritedata), [IStiUSD::RawReadCommand](/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawreadcommand), or [IStiUSD::RawWriteCommand](/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawwritecommand) methods. The minidriver defines parameter usage for **IStiUSD::Escape**.

## -see-also

[IStiDevice::Escape](/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-escape)

[IStiUSD](/windows-hardware/drivers/ddi/_image/index)
