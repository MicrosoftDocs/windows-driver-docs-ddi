---
UID: NF:sti.IStillImageW.RegisterLaunchApplication
title: IStillImageW::RegisterLaunchApplication (sti.h)
description: The IStillImage::RegisterLaunchApplication method adds an application to the still image event monitor's list of push-model aware applications.
tech.root: image
ms.date: 03/08/2023
keywords: ["IStillImageW::RegisterLaunchApplication"]
ms.keywords: IStillImageW interface [Imaging Devices],RegisterLaunchApplication method, IStillImageW.RegisterLaunchApplication, IStillImageW::RegisterLaunchApplication, RegisterLaunchApplication, RegisterLaunchApplication method [Imaging Devices], RegisterLaunchApplication method [Imaging Devices],IStillImageW interface, image.istillimage_registerlaunchapplication, sti/IStillImageW::RegisterLaunchApplication, stifnc_606c7e24-38e2-450e-a9d5-3d7018ccf9b9.xml
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
 - IStillImageW::RegisterLaunchApplication
 - sti/IStillImageW::RegisterLaunchApplication
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::RegisterLaunchApplication
---

## -description

The **IStillImage::RegisterLaunchApplication** method adds an application to the still image event monitor's list of push-model aware applications.

## -parameters

### -param pwszAppName [in]

Caller-supplied pointer to a string representing the application's "short name", which Scanners and Cameras Control Panel's property sheet will display.

### -param pwszCommandLine [in]

Caller-supplied pointer to a string representing the command line required to start the application, including the full path to the application's executable file. The current path can be obtained by calling **GetModuleFileName** (described in the Microsoft Windows SDK documentation). For more information, see the following **Remarks** section.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in *stierr.h*.

## -remarks

An application (or the application's installer) must call **IStillImage::RegisterLaunchApplication** so the still image event monitor will know of its existence. Users associate [Still Image Device Events](/windows-hardware/drivers/image/still-image-device-events) with registered applications by using Control Panel's property sheet interface. After a user has associated a device event with the application, the event monitor will start the application when the event occurs.

The method writes the application's load path in the registry. Therefore, the method should be called each time the application runs, because the user might have moved the file and **GetModuleFileName** always returns the current file location.

You can include command arguments in the application's command line. When starting a registered application, the event monitor appends the following two arguments to the command line:

| Command line argument | Description |
|---|---|
| **/StiDevice:***InternalDeviceName* | *InternalDeviceName* is the internal device name of the device for which the application is being started. |
| **/StiEvent:***EventGUID* | *EventGUID* is the string representation of the GUID for the device event that has occurred. |

The application can obtain the values specified for these arguments by calling [IStillImage::GetSTILaunchInformation](/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)).

Before calling **IStillImage::RegisterLaunchApplication**, clients of the **IStillImage** COM interface must call [IStillImage::StiCreateInstance](/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)) to obtain an **IStillImage** interface pointer.
