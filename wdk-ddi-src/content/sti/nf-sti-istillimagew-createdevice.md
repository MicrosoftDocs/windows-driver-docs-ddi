---
UID: NF:sti.IStillImageW.CreateDevice
title: IStillImageW::CreateDevice (sti.h)
description: The IStillImage::CreateDevice method creates an instance of the COM object that defines the IStiDevice COM Interface, and returns a pointer to the interface.
tech.root: image
ms.date: 03/08/2023
keywords: ["IStillImageW::CreateDevice"]
ms.keywords: CreateDevice, CreateDevice method [Imaging Devices], CreateDevice method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],CreateDevice method, IStillImageW.CreateDevice, IStillImageW::CreateDevice, image.istillimage_createdevice, sti/IStillImageW::CreateDevice, stifnc_07253e3c-b24e-4557-885f-3e17fb5dc293.xml
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
 - IStillImageW::CreateDevice
 - sti/IStillImageW::CreateDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::CreateDevice
---

## -description

The **IStillImage::CreateDevice** method creates an instance of the COM object that defines the [IStiDevice COM Interface](/windows-hardware/drivers/image/istidevice-com-interface), and returns a pointer to the interface.

## -parameters

### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling [IStillImage::GetSTILaunchInformation](/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)) or [IStillImage::GetDeviceList](/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)).

### -param dwMode

Caller-supplied constant value indicating the [Transfer Modes](/windows-hardware/drivers/image/transfer-modes) in which the device is to be used. The following values are valid.

| Mode | Description |
|---|---|
| STI_DEVICE_CREATE_BOTH | The device is being opened for both obtaining status and transferring data. |
| STI_DEVICE_CREATE_DATA | The device is being opened only for data transfers. |
| STI_DEVICE_CREATE_STATUS | The device is being opened only for obtaining status information. |

### -param pDevice [out]

Receives a pointer to the [IStiDevice COM Interface](/windows-hardware/drivers/image/istidevice-com-interface).

### -param punkOuter [in, optional]

Optional, caller-supplied pointer to the "controlling unknown" for object aggregation. See the following **Remarks** section.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

For an application to use the **IStiDevice** interface, it must first call [IStillImage::StiCreateInstance](/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)) to get a pointer to the **IStillImage** interface, then call **IStillImage::CreateDevice** to get a pointer to the **IStiDevice** interface. The pointer received in *pDevice* is used subsequently when calling **IStiDevice** methods, as illustrated in the sample still image code, to obtain access to the specified device.

If you want to create an aggregate COM object that includes **IStiDevice**, you must supply a pointer to the "controlling unknown" in *punkOuter*. In most cases you will not be creating an aggregate object, so *punkOuter* should be **NULL**. Object aggregation and the controlling unknown are described in the Microsoft Windows SDK documentation and in the *Component Object Model Specification*.

## -see-also

[IStiDevice::Release](/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-release)

[IStillImageW](/windows-hardware/drivers/ddi/_image/index)
