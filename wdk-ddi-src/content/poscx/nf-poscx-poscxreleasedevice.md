---
UID: NF:poscx.PosCxReleaseDevice
title: PosCxReleaseDevice function (poscx.h)
description: PosCxReleaseDevice is called to release a device that was previously claimed with PosCxClaimDevice. Once the device is released, the next pending claim requester is promoted.
old-location: pos\poscxreleasedevice.htm
tech.root: pos
ms.assetid: 9615915C-B729-4702-BF41-D5068B43A729
ms.date: 02/23/2018
keywords: ["PosCxReleaseDevice function"]
ms.keywords: PosCxReleaseDevice, PosCxReleaseDevice function, pos.poscxreleasedevice, poscx/PosCxReleaseDevice
f1_keywords:
 - "poscx/PosCxReleaseDevice"
 - "PosCxReleaseDevice"
req.header: poscx.h
req.include-header: Poscx.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- poscx.h
api_name:
- PosCxReleaseDevice
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxReleaseDevice function


## -description


      PosCxReleaseDevice is called to release a device that was previously claimed with
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nf-poscx-poscxclaimdevice">PosCxClaimDevice</a>.
      Once the device is released, the next pending claim requester is promoted.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

      A handle to a framework file object that identifies the caller.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The device was successfully released.</td>
</tr>
<tr>
<td><b>STATUS_ACCESS_DENIED</b></td>
<td>The calling thread is not the owner of the device.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER </b></td>
<td>The specified <i>fileObject</i> is invalid.</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nf-poscx-poscxclaimdevice">PosCxClaimDevice</a>
 

 

