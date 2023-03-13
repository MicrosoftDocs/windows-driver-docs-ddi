---
UID: NF:sti.IStiDevice.Initialize
title: IStiDevice::Initialize (sti.h)
description: This method is for internal use only.
tech.root: image
ms.date: 03/08/2023
keywords: ["IStiDevice::Initialize"]
ms.keywords: IStiDevice interface [Imaging Devices],Initialize method, IStiDevice.Initialize, IStiDevice::Initialize, Initialize, Initialize method [Imaging Devices], Initialize method [Imaging Devices],IStiDevice interface, image.istidevice_initialize, sti/IStiDevice::Initialize, stifnc_abeacac4-60ef-41f0-b70e-bf7da7fa110b.xml
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
 - IStiDevice::Initialize
 - sti/IStiDevice::Initialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice::Initialize
---

## -description

This method is for internal use only.

The **IStiDevice::Initialize** method initializes an instance of the COM object that defines the **IStiDevice** interface.

## -parameters

### -param hinst [in]

Caller-supplied instance handle of the calling process. This handle is obtained by calling **GetModuleName**(NULL).

### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling [IStillImage::GetSTILaunchInformation](/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)).

### -param dwVersion

Caller-supplied STI version number. This value must be STI_VERSION, defined in *Sti.h*.

### -param dwMode

Caller-supplied constant value indicating the [Transfer Modes](/windows-hardware/drivers/image/transfer-modes) in which the device is to be used. The following values are valid.

| Mode | Description |
|---|---|
| STI_DEVICE_CREATE_BOTH | The device is being opened for both obtaining status and transferring data. |
| STI_DEVICE_CREATE_DATA | The device is being opened only for data transfers. |
| STI_DEVICE_CREATE_STATUS | The device is being opened only for obtaining status information. |

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

The **IStiDevice::Initialize** method initializes the COM object instance that was created by calling [IStillImage::CreateDevice](/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)).

Because **IStiDevice::Initialize** is called by **IStillImage::CreateDevice**, clients of the **IStiDevice** interface do not typically call this method directly.
