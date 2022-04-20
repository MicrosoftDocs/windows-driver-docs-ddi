---
UID: NF:sti.IStillImageW.SetupDeviceParameters
title: IStillImageW::SetupDeviceParameters (sti.h)
description: The IStillImage::SetupDeviceParameters method allows clients of the IStillImage COM interface to modify a still image device's stored characteristics, if the device's bus type is unknown.
tech.root: image
ms.date: 04/18/2022
keywords: ["IStillImageW::SetupDeviceParameters"]
ms.keywords: IStillImageW interface [Imaging Devices],SetupDeviceParameters method, IStillImageW.SetupDeviceParameters, IStillImageW::SetupDeviceParameters, SetupDeviceParameters, SetupDeviceParameters method [Imaging Devices], SetupDeviceParameters method [Imaging Devices],IStillImageW interface, image.istillimage_setupdeviceparameters, sti/IStillImageW::SetupDeviceParameters, stifnc_08d945b1-ff61-4018-ae0b-5b134fc4f112.xml
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
 - IStillImageW::SetupDeviceParameters
 - sti/IStillImageW::SetupDeviceParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::SetupDeviceParameters
---

## -description

The **IStillImage::SetupDeviceParameters** method allows clients of the **IStillImage** COM interface to modify a still image device's stored characteristics, if the device's bus type is unknown.

## -parameters

### -param unnamedParam1 [in, out]

Defines the **PSTI_DEVICE_INFORMATIONW** parameter *unnamedParam1*.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

The **IStillImage::SetupDeviceParameters** method only allows modification of device parameters associated with still image devices for which a bus has not been identified. For such devices, the still image server sets the **dwHardwareConfiguration** member of the device's [STI_DEVICE_INFORMATION](/windows-hardware/drivers/ddi/sti/ns-sti-_sti_device_informationw) structure to STI_HW_CONFIG_UNKNOWN when [IStillImage::GetDeviceInfo](/previous-versions/windows/hardware/drivers/ff543782(v=vs.85)) is called.

Currently, the only device parameter that can be modified is the device's port name. When calling this method to modify the port name, the **dwSize**, **szDeviceInternalName**, and **pszPortName** members of the STI_DEVICE_INFORMATION must be specified. All other members are ignored.

Before calling **IStillImage::SetupDeviceParameters**, clients of the **IStillImage** COM interface must call [IStillImage::StiCreateInstance](/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)) to obtain an **IStillImage** interface pointer.
