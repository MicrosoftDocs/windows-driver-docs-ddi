---
UID: NF:sti.IStillImageW.SetupDeviceParameters
title: IStillImageW::SetupDeviceParameters
author: windows-driver-content
description: The IStillImage::SetupDeviceParameters method allows clients of the IStillImage COM interface to modify a still image device's stored characteristics, if the device's bus type is unknown.
old-location: image\istillimage_setupdeviceparameters.htm
tech.root: image
ms.assetid: 8fbbe6c8-bf65-42df-a4e4-cb683b567bf7
ms.date: 5/3/2018
ms.keywords: IStillImageW interface [Imaging Devices],SetupDeviceParameters method, IStillImageW.SetupDeviceParameters, IStillImageW::SetupDeviceParameters, SetupDeviceParameters, SetupDeviceParameters method [Imaging Devices], SetupDeviceParameters method [Imaging Devices],IStillImageW interface, image.istillimage_setupdeviceparameters, sti/IStillImageW::SetupDeviceParameters, stifnc_08d945b1-ff61-4018-ae0b-5b134fc4f112.xml
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	sti.h
api_name:
-	IStillImageW.SetupDeviceParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::SetupDeviceParameters


## -description


The <b>IStillImage::SetupDeviceParameters</b> method allows clients of the <b>IStillImage</b> COM interface to modify a still image device's stored characteristics, if the device's bus type is unknown.


## -parameters






#### - pDevInfo [in, out]

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548361">STI_DEVICE_INFORMATION</a> structure describing a still image device.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::SetupDeviceParameters</b> method only allows modification of device parameters associated with still image devices for which a bus has not been identified. For such devices, the still image server sets the <b>dwHardwareConfiguration</b> member of the device's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548361">STI_DEVICE_INFORMATION</a> structure to STI_HW_CONFIG_UNKNOWN when <a href="https://msdn.microsoft.com/library/windows/hardware/ff543782">IStillImage::GetDeviceInfo</a> is called.

Currently, the only device parameter that can be modified is the device's port name. When calling this method to modify the port name, the <b>dwSize</b>, <b>szDeviceInternalName</b>, and <b>pszPortName</b> members of the STI_DEVICE_INFORMATION must be specified. All other members are ignored.

Before calling <b>IStillImage::SetupDeviceParameters</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.



